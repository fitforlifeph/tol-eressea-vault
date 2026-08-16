---
title: "Heart Rate Variability Derived Aerobic Threshold Estimation"
author: ""
publication: "Google Colab"
published: 
saved: 2026-08-16T07:44:05.129820+00:00
created: 2026-08-16T07:44:05.129820+00:00
source: "https://colab.research.google.com/drive/1GUZVjZGhc2_JqV-J5m1mgbvbiTBV9WzZ"
estimated_pages: 11
status: complete
draft: false
tags: []
---

# Heart rate variability (HRV) derived aerobic threshold estimation

In this notebook I have implemented a simple script to compute *alpha 1* from detrended fluctuation analysis (DFA), a method proposed in literature [1] to estimate the aerobic threshold based on HRV data. Special thanks to Raúl Celdrán, Alan Couzens and James Cobb for stimulating this conversation on Twitter, and to Bruce Rogers and Thomas Gronwald, authors of the paper just cited, who followed up with more research and resources. **Feel free to comment [here](https://twitter.com/altini_marco/status/1337696020394893314) for any feedback or findings linked to this notebook**, while you can find answers to common questions, [here](https://www.hrv.tools/hrv-logger-faq.html)


**If you are not into coding, I have implemented Detrended Fluctuation Analysis (DFA) in the latest update of the [Heart Rate Variability (HRV) logger app](https://apps.apple.com/us/app/heart-rate-variability-logger/id683984776)**, just released on the apple store and on **[Google Play](https://play.google.com/store/apps/details?id=com.asma.hrvlogger)**. You can get the same analysis just linking your chest strap to the app, as shown [here](https://twitter.com/altini_marco/status/1340345906072326144).

The full text of the paper can be found [here](https://www.frontiersin.org/articles/10.3389/fphys.2020.550572/full). According to the paper, **a value of alpha close to 0.75 should correspond to the aerobic threshold, while alpha should approximate 0.5 as intensity increases** past the anaerobic threshold.

DFA's alpha was also investigated in [2] (link [here](https://www.researchgate.net/profile/Denis_Mottet2/publication/7194410_Non-Linear_Analyses_of_Heart_Rate_Variability_During_Heavy_Exercise_and_Recovery_in_Cyclists/links/09e415048cf4cd4818000000.pdf)), showing similar results, with alpha equal to 1 at rest and at 40% of VO2max, and reducing to 0.5 at 90% VO2max.

This method seems particularly interesting as it **does not require an incremental test and could therefore be easier to implement in practice** as an additional check for exercise intensity. Since no incremental test is required, we can use this workbook with any workout file to compute *alpha 1* and see if the scores reflect our knowledge of the aerobic threshold for a given athlete and workout

[1] Gronwald, T., Rogers, B., & Hoos, O. (2020). Fractal correlation properties of heart rate variability: A new biomarker for intensity distribution in endurance exercise and training prescription?. Frontiers in Physiology, 11, 1152.

[2] Le Gallais, D. (2005). Non-linear analyses of heart rate variability during heavy exercise and recovery in cyclists. Int J Sports Med, 26, 1-6.

Important prerequisites:

*   **You need an accurate chest strap**. Unfortunately many chest straps are able to provide accurate heart rate data but do not provide accurate beat to beat data for HRV analysis (RR intervals). To make the matter worse, **many chest straps (all?) still provide RR intervals on top of the recorded averaged heart rate, even when they are unable to compute them accurately, making it difficult even to understand if we are collecting usable data or not**. My recommendation is to use a Polar H7 or H10, as these have both been validated in their ability to measure accurately RR intervals.



*   **You need a *.fit* or *csv* file including RR intervals**. We will explore both options below, either of the approaches will work as long as you have a reliable chest strap, so feel free to pick the easiest given your setup.

## Fit file
A *fit* file can be recorded typically by linking a watch like a Garmin to a chest strap, and enabling HRV data collection (I've learnt this from Alan Couzens, see how to configure your watch, in his post [here](https://alancouzens.com/blog/get_hrv_data_from_fit_file.html)). If you do not have a simple way to record data to a *fit* file or the script below does not work for your fit files (which can happen as different brands seem to be storing RR intervals differently in their *fit* files), then use the second approach, loading a *csv* file.

## Csv file
You can record a csv file including RR intervals collected from your chest strap, using the [Heart Rate Variability Logger](https://apps.apple.com/us/app/heart-rate-variability-logger/id683984776) app. This is a research app we made to collect and export data from external sensors, hence it works with any bluetooth device, but again, make sure your strap is accurate first. Once you have recorded data with the HRV Logger app, use the export function to export csv files (normally the files include heart rate, RR intervals, HRV features and annotated events).

Let's start by installing a few libraries needed to process the *.fit* or *csv* file as well as plot the data using ggplot:

```python
%pip install fitparse
%pip install plotnine

import csv
import fitparse
from plotnine import *
```

and load a few common libraries:

```python
import numpy as np
import pandas as pd
import seaborn as sn
import matplotlib.pyplot as plt
import math
```

# Loading the data

First we can mount our Google Drive, so that files remain available in the future. You most likely **need to edit these steps to load your own file**

For this example, I am loading a 90 minutes run with a slightly faster finish. The run was otherwise around my aerobic threshold

```python
from google.colab import drive
drive.mount('/content/gdrive')
```

Now we can read our data. As mentioned earlier we have two options, so use only one of the two approaches below, either run the first line for the *fit* file or run the second line for the *csv* file. If you use the *csv* file, make sure to load the RR intervals file, which always includes the data and _RR_ in the file name when exported from the HRV Logger:

```python
fit_file = fitparse.FitFile('/content/gdrive/MyDrive/Colab Notebooks/Data/Thresholds/aerobic_harderfinish.fit')
# load RR intervals from the fit file
RRs = []
for record in fit_file.get_messages('hrv'):
        for record_data in record:
          for RR_interval in record_data.value:
            if RR_interval is not None:
              RRs.append(RR_interval)
```

**Do not use the code below if you have already loaded your data** from a *fit* fie.

```python
logger_file = pd.read_csv('/content/gdrive/MyDrive/Colab Notebooks/Data/Thresholds/2020-12-10_RR_easy run.csv')
# here we keep only the RR intervals so that the rest of the code is the same regardless of what data you loaded
RRs = []
RRs = logger_file.iloc[:, 1]/1000 #same format as fit file
RRs = RRs.tolist()
```

From now on, the code is the same no matter how you loaded your data

# Removing artifacts and plotting the RR intervals

Now borring Alan's code, we get the RR intervals from the *.fit* file, remove artifacts and compute timestamps. Here I have also reduced the allowed beat to beat difference as I have noticed that my strap includes quite some artifacts when using the standard 20-25% threshold recommended for resting measurements. Obviously during exercise the beat to beat differences are minimal (almost zero as a matter of fact), and therefore we can be a bit more strict with our thresholds. **Always make sure to plot your data with and without artifact correction to see visually if you had any artifacts and if the procedure worked well**, otherwise none of what we will compute later will make any sense (HRV is highly affected by even minimal artifacts). Finally, we create a data frame to manipulate the data more easily later on.

Note for Suunto users: if you use a Suunto, the code below might not work as the format is slightly different. Please refer to [this edit](https://twitter.com/StefanMurnau/status/1337855406572449792/photo/1) and you should be able to get it to work.

```python
artifact_correction_threshold = 0.05
filtered_RRs = []
for i in range(len(RRs)):
  if RRs[(i-1)]*(1-artifact_correction_threshold) < RRs[i] < RRs[(i-1)]*(1+artifact_correction_threshold):
        filtered_RRs.append(RRs[i])

x = np.cumsum(filtered_RRs)

df = pd.DataFrame()
df['timestamp'] = x
df['RR'] = filtered_RRs
```

Always plot your data, it is really easy to get this wrong just because we are using the wrong strap or leaving artifacts in the RR intervals time series:

```python
(ggplot(df)
    + aes(x='timestamp', y='RR')
    + geom_line()
    + labs(title="RR intervals", x='Seconds', y="Milliseconds")
    )
```

As we can see from the plot above, RR intervals are rather stable for the first hour, in which the effort is around my aeroibic threshold. Then we have some spikes, those are simply breaks (traffic lights), which of course reduce heart rate (hence higher RR intervals, which are the inverse of instantaneous heart rate). Finally, as I push a bit harder towards the end of the workout, we have lower RR intervals

# Computing Detrended Fluctuation Analysis (DFA) and alpha 1
In an earlier version of this notebook we used pyhrv to compute DFA. However, using a third party library sometimes hides some of the parameters used to compute DFA, and makes it more difficult to compare results between different implementations. Hence, I have now added a "manual" implementation of DFA, which you can find below. Credit for this code goes to [Sarah Pickus](https://github.com/pickus91/HRV), a former colleague of mine, whose code I have adapted for this script. As you can see we are using linear fitting:

```python
def DFA(pp_values, lower_scale_limit, upper_scale_limit):
    scaleDensity = 30 # scales DFA is conducted between lower_scale_limit and upper_scale_limit
    m = 1 # order of polynomial fit (linear = 1, quadratic m = 2, cubic m = 3, etc...)

    # initialize, we use logarithmic scales
    start = np.log(lower_scale_limit) / np.log(10)
    stop = np.log(upper_scale_limit) / np.log(10)
    scales = np.floor(np.logspace(np.log10(math.pow(10, start)), np.log10(math.pow(10, stop)), scaleDensity))
    F = np.zeros(len(scales))
    count = 0

    for s in scales:
        rms = []
        # Step 1: Determine the "profile" (integrated signal with subtracted offset)
        x = pp_values
        y_n = np.cumsum(x - np.mean(x))
        # Step 2: Divide the profile into N non-overlapping segments of equal length s
        L = len(x)
        shape = [int(s), int(np.floor(L/s))]
        nwSize = int(shape[0]) * int(shape[1])
        # beginning to end, here we reshape so that we have a number of segments based on the scale used at this cycle
        Y_n1 = np.reshape(y_n[0:nwSize], shape, order="F")
        Y_n1 = Y_n1.T
        # end to beginning
        Y_n2 = np.reshape(y_n[len(y_n) - (nwSize):len(y_n)], shape, order="F")
        Y_n2 = Y_n2.T
        # concatenate
        Y_n = np.vstack((Y_n1, Y_n2))

        # Step 3: Calculate the local trend for each 2Ns segments by a least squares fit of the series
        for cut in np.arange(0, 2 * shape[1]):
            xcut = np.arange(0, shape[0])
            pl = np.polyfit(xcut, Y_n[cut,:], m)
            Yfit = np.polyval(pl, xcut)
            arr = Yfit - Y_n[cut,:]
            rms.append(np.sqrt(np.mean(arr * arr)))

        if (len(rms) > 0):
            F[count] = np.power((1 / (shape[1] * 2)) * np.sum(np.power(rms, 2)), 1/2)
        count = count + 1

    pl2 = np.polyfit(np.log2(scales), np.log2(F), 1)
    alpha = pl2[0]
    return alpha
```

# Computing features

Alright, if the data looks good and artifact free, we can proceed and compute different HRV features. For this purpose, **we need to determine the features computation window**. The window length will have an impact as some features can only be computed with a few minutes of data (for example the low frequency power), while other features are relatively stable even with just a few seconds of data (rMSSD for example).

Additionally, **there are trade offs between the amount of data to be used (in theory the more the better) and the issue of computing features during a relatively stable period**, in which we have a steady state (intensity and heart rate are not changing that much).

Hence, **my recommendation would be to use either a workout with a stable / constant effort at low intensity (and maybe try a few files to see if you can find differences in alpha 1 just below or above your aerobic threshold), or to use a progression workout**, in which the intensity is relatively stable for at least 5-8 minutes at each step. This way we should get features representative of what we are trying to capture, otherwise the effect of recoveries, short intervals, etc. - will create issues for this analysis as we are not looking at instantaneous heart rate values, but we are using a few minutes of data to compute HRV features

For the computations below, I have picked **2 minutes as the window length**, which should work decently for most features (and is also the window length recommended in [1]). You can change this parameter editing the *step* variable, which is the window length in seconds. The lower and upper scale for DFA are other important parameters. In literature, they are typically set to 4 and 16 [1]:

```python
def computeFeatures(df):
  features = []
  step = 120
  for index in range(0, int(round(np.max(x)/step))):

      array_rr = df.loc[(df['timestamp'] >= (index*step)) & (df['timestamp'] <= (index+1)*step), 'RR']*1000
      # compute heart rate
      heartrate = round(60000/np.mean(array_rr), 2)
      # compute rmssd
      NNdiff = np.abs(np.diff(array_rr))
      rmssd = round(np.sqrt(np.sum((NNdiff * NNdiff) / len(NNdiff))), 2)
      # compute sdnn
      sdnn = round(np.std(array_rr), 2)
      #dfa, alpha 1
      alpha1 = DFA(array_rr.to_list(), 4, 16)

      curr_features = {
          'timestamp': index,
          'heartrate': heartrate,
          'rmssd': rmssd,
          'sdnn': sdnn,
          'alpha1': alpha1,
      }

      features.append(curr_features)

  features_df = pd.DataFrame(features)
  return features_df
```

We now have a new data frame with HRV features computed every 3 minutes:

```python
features_df = computeFeatures(df)
features_df.head()
```

# Analyzing results

Let's look at *alpha 1*. According to the papers, you should see the following:


*   Values close to 1 for very low intensity efforts (40% of VO2max)
*   Values close 0.75 for the aerobic threshold
*   Values close to 0.5 for anything beyond the anaerobic threshold

```python
(ggplot(features_df)
    + aes(x='timestamp', y='alpha1')
    + geom_point()
    + geom_line()
    + scale_y_continuous(limits = [0, 1.5]) # this seems to be the range of meaningful values
    + labs(title="Plot of alpha 1 as derived from DFA for aerobic threshold estimation", x='Window', y="alpha 1"))
```

Finally, assuming we have loaded a constant effort, we can also compute the average *alpha 1*:

```python
round(np.mean(features_df['alpha1']), 2)
```

In this example file, we have an average *alpha 1* that is exactly what it should be according to literature (0.75 for an effort close to aerobic threshold). So far so good. However, I was a bit surprised not to see a reduction in *alpha 1* as I was pushing harder towards the end of the workout.

I have also tried slower runs and found the average *alpha 1* to be indeed a bit higher, but the question at this point remains if this piece of information is more informative than heart rate alone. I'm curious to collect more data and see the results.

# Update #1: clean up and color coding
I have just discussed above how some of the data might not be relevant as we are not in a steady state (for example the change in heart rate shown when stopping at a traffic light), hence a small change we could implement is to remove those data points automatically.

For this purpose, we can use the SDNN value, as this feature captures the overall variation around the mean for a computation window, and therefore even if the beat to beat differences stay small (as shown in a small rMSSD), the overall variations from the mean of the window can be large during recoveries. Let's use a simple threshold to remove alpha 1 scores computed on non-steady state data as derived from SDNN data:

```python
threshold_sdnn = 10 #rather arbitrary, based on visual inspection of the data
features_df_filtered = features_df.loc[features_df['sdnn'] < threshold_sdnn, ]

(ggplot(features_df_filtered)
    + aes(x='timestamp', y='alpha1')
    + geom_point()
    + geom_line()
    + scale_y_continuous(limits = [0, 1.5])
    + labs(title="Alpha 1 as derived from DFA for aerobic threshold estimation", x='Window', y="alpha 1"))
```

It seems that we were able to remove a few of the less relevant data points. Something else that we can do is to use a different color coding, since this method does not require locating inflection points or person-specific thresholds:

```python
(ggplot(features_df_filtered)
    + aes(x='timestamp', y='alpha1', color = 'alpha1')
    + geom_point()
    + geom_line()
    + scale_y_continuous(limits = [0, 1.5])
    + scale_color_gradient(low="red",high="yellow", limits = [0, 1.5])
    + labs(title="Alpha 1 as derived from DFA for aerobic threshold estimation. Average alpha 1: " + str(round(np.mean(features_df_filtered['alpha1']), 2)), x='Window', y="alpha 1"))
```

```python
round(np.mean(features_df_filtered['alpha1']), 2)
```

Which gives a mostly orange line, as expected since we are in the middle of the range (0 - 1.5, with the aerobic threshold set to approximately 0.75). Here is what is reported in the paper linked at the beginning of this post [1], for an incremental test carried out by two people of different fitness levels (as shown by their VO2max):

Note that in our data, we are using a rather constant effort, not an incremental test, and therefore we expect *alpha 1* to be stable

Possible extensions at this point could be the following:


1.   **Use data from an incremental test** (doesn't have to be maximal) to see if *alpha 1* tracks well with changes in intensity
2.   **Load different workouts of various intensities and plot the average external load (e.g. power or pace) against the average *alpha 1* of each workout**, to analyze the relationship between the two, which should be similar to what we see in an incremental test

# Update #2: deriving aerobic threshold heart rate

In this section, we will use our workout data to estimate aerobic threshold based on the suggested Alpha 1 = 0.75. We can do so with any workout, but it would probably be better to have some sort of progression for our regression model to work best. Let's load another file, in which I went for an easy run on the treadmill, slowly increasing intensity until I was past the aerobic threshold, and then reducing it again.

```python
logger_file = pd.read_csv('/content/gdrive/MyDrive/Colab Notebooks/Data/Thresholds/2020-12-19_RR_Treadmill.csv')
# here we keep only the RR intervals so that the rest of the code is the same regardless of what data you loaded
RRs = logger_file.iloc[:, 1]/1000 #same format as fit file
RRs = RRs.tolist()
# remove artifacts and create data frame
artifact_correction_threshold = 0.05
filtered_RRs = []
for i in range(len(RRs)):
  if RRs[(i-1)]*(1-artifact_correction_threshold) < RRs[i] < RRs[(i-1)]*(1+artifact_correction_threshold):
        filtered_RRs.append(RRs[i])

x = np.cumsum(filtered_RRs)

df = pd.DataFrame()
df['timestamp'] = x
df['RR'] = filtered_RRs
# compute features using the function we defined earlier
features_df = computeFeatures(df)
print(features_df.head())
```

Here we'll keep it really simple and build a linear model to estimate heart rate given alpha 1:

```python
from sklearn.linear_model import LinearRegression

length = len(features_df['alpha1'])
reg = LinearRegression().fit(features_df['alpha1'].values.reshape(length, 1), features_df['heartrate'].values.reshape(length, 1))
prediction = reg.predict(np.array(0.75).reshape(1, 1))
print(math.floor(prediction))
```

For this file, I get 144 bpm, which sounds about right for me (my heart rate max is 187, hence the aerobic threshold should be at about 78% of max, which is 145-146). Normally I would consider anything below 150 as my Z1-Z2. Let's plot this relationship:

```python
(ggplot(features_df)
    + aes(x='heartrate', y='alpha1', color = 'alpha1')
    + geom_point()
    + geom_line()
    + scale_color_gradient(low="red",high="yellow", limits = [0, 1.5])
    + labs(title = 'Estimated aerobic threshold heart rate (alpha 1 = 0.75): ' + (str(math.floor(prediction[0].item()))) + " bpm", x='bpm', y="alpha 1"))
```

That's all for this second update.

# Useful resources
Since I posted this notebook I got in contact with Bruce Rogers and Thomas Gronwald, authors of the paper linked above, and also of [this one](https://www.frontiersin.org/articles/10.3389/fphys.2020.596567/abstract) just published. Bruce has a really nice blog covering in more detail this approach and providing many examples. Check it out at [this link](http://www.muscleoxygentraining.com/2020/12/dfa-a1-calculation-kubios-vs-python.html).

For any questions or issues on this notebook, drop me a line [here](https://twitter.com/altini_marco/status/1337696020394893314).