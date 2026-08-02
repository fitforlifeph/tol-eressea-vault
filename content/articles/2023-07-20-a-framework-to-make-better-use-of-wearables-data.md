---
title: "A framework to make better use of Wearables data"
author: "Marco Altini"
publication: "Marco Altini’s Substack"
published: 2023-07-05
saved: 2023-07-20T02:47:37.139369+00:00
created: 2023-07-20T02:47:37.139369+00:00
source: "https://marcoaltini.substack.com/p/a-framework-to-make-better-use-of"
estimated_pages: 19
status: complete
draft: false
pdf_url: "https://archive.javierpgomez.com/articles/2023-07-20-a-framework-to-make-better-use-of-wearables-data.pdf"
tags: []
---

# A framework to make better use of Wearables data

### measurements, estimates and more

When it comes to wearables, I often see **either blindly embracing a device** (i.e. fanboy kind of attitude, or sponsored athlete), **or dismissing it entirely** because of e.g. an inaccuracy in a metric provided (e.g. skeptical coach or scientist).

Unfortunately, **we need to be a lot more nuanced about these devices and their use**. 

With this blog, I want to try to provide a framework that can allow you to make better use of the data. I truly believe there is a lot to gain from using these devices, in terms of **awareness and actionability**, but we need to move past the dichotomy above.

In particular, **we need to understand what is measured** (and *when*), **and what is estimated** (and *how*). 

Once we understand these differences, we can start spending our time and energy on what is likely more reliable and useful.

# Types of metrics

A wearable typically provides a number of metrics, for example, heart rate, heart rate variability (HRV), temperature, oxygen saturation (SPO2), calories burnt, stress level, readiness or recovery scores, sleep stages, sleep quality scores, etc.

The first important point to understand is that these **metrics are not all derived in the same way**, which has big implications for their accuracy. 

This is an important point because, despite my criticism of these devices and the obnoxious way some of the companies selling them do business, **it is incorrect to assume that because of e.g. an inaccuracy in a certain parameter** (in a given context, e.g. heart rate during exercise) **the data is also inaccurate for all other parameters**.

We need to get past this thinking, as this is not how wearables work. If you are bad at one thing, you are likely not bad at everything - are you? It is the same here.

The issue is of course that the devices are marketed as great at everything, with little or no transparency on signal quality, measurement error, estimate error, etc. - and therefore we have to do this type of work ourselves, which isn’t easy.

Let’s get to it then.

# Measurements and estimates

When we measure something, we determine its ~exact value (give or take a measurement error). **To measure something, we need a sensor that can do the job**, according to what is an established method to measure such parameter. For example, a wearable can include a sensor that can measure changes in blood flow as the heart beats, and therefore - under certain circumstances - can measure your heart rate. 

**When we estimate something, we take a guess**. We can take this guess in different ways, from simple (e.g. determining your maximal heart rate based on your age) to more complex (e.g. determining your sleep stages using a machine learning model whose inputs are a number of heart rate variability, movement, temperature, and circadian features). In both cases, this is just a guess. To actually measure your maximal heart rate you would need to do a maximal test (or similar). To actually measure your sleep stages you would need to measure brain waves, eye movement, and muscle activity - none of these things are measured by a wearable when providing sleep stages.

The distinction between measurements and estimates is an important one because it already allows us to draw a line between **things that our device can capture because of the sensors that are included, and things that our device is trying to guess because they might be somewhat related to the other parameters that the sensors can measure**. 

Let’s cover in a bit more detail measurements, before moving to estimates.

## Measurements and the *when*

Above I mentioned how, for example, a wearable can include a sensor that can measure changes in blood flow as the heart beats, and therefore - under certain circumstances - can measure your heart rate. Here I want to focus on when we take a measurement because this has implications for the accuracy and the interpretability of the data (context).

### The *when* in terms of accuracy

I’ve also mentioned how measurements differ from estimates (or guesses), in a way that tells us already that measurements are really what we should be focusing on most of the time. However, **measurements are not perfect either, as we can always have measurement errors, and these errors might depend on when we take a measurement**. In the context of heart rate, we know that optical technology (those lights flashing in green at the bottom of your wearable) doesn't work very well when we are moving. In particular, **the more movement at the wrist, the lower the signal quality, and the higher the error**. At rest, optical technology is great, but during movement, it is quite inaccurate. 

How do we determine when a measurement can be trusted?

**The good thing about measurements is that they can be easily evaluated against a reference device**. For heart rate, we can use an electrocardiogram device and stick electrodes on our body, or a more user-friendly version (e.g. a Polar chest strap) and compare the data with what we get from our wearable. The same applies to HRV but with even more strict requirements: **only in the complete absence of movement, HRV can be measured with optical sensing**. Even just contracting your muscles while you type on a keyboard, will make the data garbage (see [these tests](https://medium.com/@altini_marco/using-the-whoop-band-for-on-demand-heart-rate-variability-hrv-analysis-78eabd265189)). This is important to remember: **data is good and consistent between devices only if you are not moving at all** (the error is more than doubled by just "sitting").

Context matters: if a device is good for HRV at night it does not mean in any way that the same can be done during the day nor that heart rate during movement would be accurate etc. - the contrary is also true: if a device doesn’t work for heart rate during exercise it does not mean that you should dismiss it for heart rate at rest or HRV. Ask for proof. Look for validations (even something provided by the companies themselves would be a good starting point).

### The *when* in terms of interpretability

Let’s say we measure a certain physiological parameter like HRV, and we do so at rest, when not moving (not even typing). We have checked all the boxes above: we are using a measurement, not an estimate (of pulse rate variability, if not HRV, see also [this blog](https://marcoaltini.substack.com/p/blood-flows-when-the-heart-beats)), and we are measuring in the right context, i.e. when there is no movement. That’s great, but **certain parameters are only meaningful when measured at a certain time, and therefore there is one more aspect to take into account: the time of the measurement**.

I will use here the example of HRV as that’s my area of expertise, but you can probably envision similar issues for other parameters. When it comes to HRV, without going into too many details, our goal is to capture the body’s stress response. To do so, we need to measure at rest, and far from stressors. The only way to do so is to measure first thing in the morning (spot check) or continuously during the night. There is simply no other way. However, wearables might provide you with random data points collected during the day or night (e.g. as the Apple Watch does, which I discuss in more detail [here](https://marcoaltini.substack.com/p/apple-watch-and-heart-rate-variability)), making the data of no use even if accurate.

We need accurate and meaningful data. Meaningful typically means measured at the right time.

## Measurements takeaways

Measurements are what we should be focusing on under most circumstances, as these are not guessed from other parameters, but are actually measured by the sensors available on the wearable.

Measurements can have larger errors in certain contexts, e.g. heart rate or HRV when we are moving, might be inaccurate (heart rate), or even impossible to compute (HRV).

Finally, **measurements need to be taken at the right time to be meaningful in terms of interpretability, and despite the push to “measuring all the time”**, often a desperate attempt to keep you “engaged” with their toy, **there is often no use in this approach** (for example, I cover how meaningless continuous HRV is, in [this](https://marcoaltini.substack.com/p/a-quick-note-on-continuous-heart) blog). 

**Here are some measurements you can trust**, in many wearables:

- **heart rate at rest** (most wearables), if you are provided with an average of the night or with the possibility to take a spot check measurement first thing in the morning. This can be useful to track acute responses to large stressors (e.g. sickness, excessive alcohol intake), and chronic changes in relation to e.g. cardiorespiratory fitness, environmental stressors, etc.
- **HRV at rest** (some wearables, this is a bit more complex), if you are provided with an average of the night or with the possibility to take a spot check measurement first thing in the morning. This can be useful to track acute and chronic responses to stressors (e.g. training, sickness, traveling, alcohol intake, menstrual cycle, psychological stressors, etc.). See how,[here](https://marcoaltini.substack.com/p/whats-your-normal-range-for-heart) .
- skin temperature at rest, e.g. in relation to sickness or the menstrual cycle.

While here are some **measurements that you should be more skeptical of**:

- **heart rate during exercise** , especially if there are a lot of vibrations or wrist movements, which are known to completely disrupt the signal. At your next Grand Slam, please leave it at home.
- **HRV** measured outside of the night or outside of measurements you are intentionally taking while not moving, basically any form of automated measurement and resulting stress estimate.

Note how **you do not need to wear the wearable during the day to measure the only parameters that can actually be measured accurately**. This is why I wear my Oura ring only when I sleep so that I can get a measurement of my average night HRV and resting heart rate. 

In most wearables, nothing else is measured, but it is estimated. Let’s now look at these estimates.

See also:

- [Blood flows when the heart beats](https://marcoaltini.substack.com/p/blood-flows-when-the-heart-beats) .
- [What’s your normal range for HRV?](https://marcoaltini.substack.com/p/whats-your-normal-range-for-heart)
- [Apple Watch and Heart Rate Variability (HRV): a complicated relationship](https://marcoaltini.substack.com/p/apple-watch-and-heart-rate-variability) .
- [Stability in heart rate variability.](https://marcoaltini.substack.com/p/stability-in-heart-rate-variability)

## Estimates of known and unknown parameters 

When it comes to estimates, I think we can make another useful distinction, i.e. the one between estimates of known parameters and estimates of unknown parameters.

What’s the difference? **Estimates of known parameters are attempts to guess the value of something that could be measured using a different technology**. On the other hand, estimates of unknown parameters are made up scores that cannot possibly be evaluated (maybe that’s why companies like them so much). 

### Known parameters

An example of known parameters is calories, which are estimated using movement data derived from an accelerometer, sometimes combined with heart rate data derived from an optical sensor. We could however measure calories using direct calorimetry, which is not very practical. Similarly, sleep stages are estimated from heart rate variability features, movement, temperature, etc. - but we can check the accuracy of these estimates against polysomnography, the reference system for this application. These are all estimates of known parameters.

The good thing about **estimates of known parameters** is that **we can check the accuracy** of the estimate: we can use a wearable together with the actual reference device, and see what is the error, ideally in a number of different contexts (e.g. rest vs exercise) and people. 

Unfortunately, reference systems are typically very expensive and have little ecological validity (i.e. the way you use them, has nothing to do with how you actually go about your day or night). **My recommendation is to look for papers validating a device so that you can get an idea of what is the estimate error, and if the data you get should be worth your attention, or not**. 

As wearables move faster than academia, we might also have no published literature yet. **A good heuristic in my view, is to compare or look for comparisons of multiple devices** (ideally from people that know what they are doing, it is easy to misuse tools or it could be that users might not know what is an acceptable difference or how a metric should be evaluated). **If the output of multiple wearables for a given parameter is inconsistent, it is a clear red flag that you should not be bothering with this parameter**. 

Consider that each wearable company has hundreds of really smart people working for them. If the result of this work is all over the place (e.g. sleep time or stages when using multiple wearables), then it probably means that we are simply unable to estimate such parameters well enough.

Once again, remember that being bad at one thing does not necessarily mean being bad at all the things (and the other way around) - we cannot dismiss the wearables altogether because of a bad estimate.

**Some important points about estimates**:

- **Do not generalize from measurements** : we should never assume that because a device is good at measuring something (e.g. an Apple Watch can measure resting heart rate with high accuracy) it is also good at estimating something (e.g. an Apple Watch is not good at estimating SPO2). See the figure below.

- **Error compounds** : estimates are guesses and when we make an estimate on top of an estimate (as often wearables do), error compounds. If we measure heart rate, which also might have some error (artifacts), then we use it to estimate sleep stages, which typically have quite a large error, then we use these sleep stages and activity (with an error too, for example, if our activity did not involve much wrist motion) to estimate recovery or readiness, then we have put errors over errors over errors. What do we expect?
- **Validations or inconsistencies in output** . As wearables move faster than academia, we might also have no published literature yet. A good heuristic in my view, is to compare or look for comparisons of multiple devices. If the output of multiple wearables for a given parameter is inconsistent, it is a clear red flag that you should not be bothering with this parameter: we are unable to estimate it reliably.

To clarify these points, I use the excellent work of Peter Tierney as an example. When looking at measurements, heart rate between devices is the same:

When moving to estimates, let's call them simple estimates, like sleep time, we can have large errors on any given day (e.g. more than an hour), but the trend seems to be captured reasonably well (for this person - keep in mind that individual differences in behavior can cause issues, e.g. I can’t get any wearable to work properly because I read a kindle in bed):

When moving to more complex estimates, things seem to be all over the place, which makes me quite skeptical about our ability to get any meaningful insights with these devices (despite having developed and validated one of these models myself):

### Unknown parameters

Unknown parameters are quantities that “do not really exist” and cannot be measured with any other device. For example, most made-up scores or metrics like readiness and recovery scores, sleep quality scores, strain, stress scores, etc.

I have discussed in detail recovery and readiness scores and HRV in [this blog](https://medium.com/@altini_marco/on-heart-rate-variability-hrv-and-readiness-394a499ed05b), but here I just want to highlight some important points. 

Wearables provide a recovery or readiness score for a simple reason: **they track many parameters and try to break down that information into something more digestible** for the consumer, which means generating a single recovery or readiness score.

However, the most important question for me, when looking at such scores, is always the following: **did my behavior or my physiology trigger a reduced score?** Did I get a low score because my HRV was low or because yesterday I was very active or I slept a bit less? In my opinion, **what we should care about is our body’s physiological response, and that is what resting physiology captures (the output, not your behavior, which is the input)**. If your physiology is fine, it means your body did not respond poorly to a disruption in sleep, and therefore we might not need to penalize your score because of sleep. Let alone that **if you adjust your activity or sleep duration on some of today’s wearables, your readiness will change**. To me, this is a red flag given the inability of such wearables to estimate accurately either sleep or activity. Note that even if they were perfectly estimated, **physiology (the output) already reflects what you need to know**. **All other parameters (sleep, activity, etc.) are inputs and become essential as contextual information, to understand how your physiology changes in relation to sleep or exercise habits for example**, but this is different from using them directly to determine your ability to perform on a given day. 

Including activity or sleep in readiness or recovery scores can give you the perception that these scores are meaningful, you went hard and the score is low, but **if there is a systematic impact of physical activity (or other stressors) on recovery and readiness scores, unrelated to your actual physiological response, then why do you even measure your physiology?** If I go for a hard run, the day after I want to see how my body dealt with it (my resting physiology, for example resting heart rate and HRV), I do not want to get a readiness score that penalizes me for having done a hard effort or having slept a bit less. This is why in [HRV4Training](http://hrv4training.com/) we don’t create a score combining multiple parameters, the score is HRV.  

As per other made-up scores, keep in mind that there is no objective way to quantify sleep quality or stress either, and in most cases, wearables do not have the required context and would oversimplify your physiological response (e.g. no movement and heart rate a bit higher, you must be stressed, or high HRV? you must be ready to perform - which is not always the case, as I discuss [here](https://marcoaltini.substack.com/p/abnormally-high-heart-rate-variability)). 

#### What is your goal?

Are you using a wearable because you are interested in blind guidance or are you interested in understanding your body’s response to various stressors you face?

This is a key question to ask yourself.

In some circumstances, made-up scores might have a place. Blind guidance from a wearable or app without a plan is why readiness and recovery scores exist. The scores try to include various aspects of your life (activity, sleep, HRV, etc.) so that the app can do the decision-making for you. This of course makes sense as we do not all have a coach or the time or energy or knowledge to look at the raw data and interpret it. It is easier to look at a cumulative readiness score making a few simple assumptions (e.g. less sleep and more activity equals lower readiness) than to look at physiological data ([heart rate and HRV](https://medium.com/@altini_marco/resting-heart-rate-and-heart-rate-variability-hrv-whats-the-difference-part-1-1c6b3b769324)) and at [how physiology changes in response to the various stressors](https://medium.com/@altini_marco/the-ultimate-guide-to-heart-rate-variability-hrv-part-3-5fe902f3d2b3) [you](https://medium.com/@altini_marco/the-ultimate-guide-to-heart-rate-variability-hrv-part-3-5fe902f3d2b3) [face](https://medium.com/@altini_marco/the-ultimate-guide-to-heart-rate-variability-hrv-part-3-5fe902f3d2b3).

**If you are able to link an app’s or wearable readiness score to how you feel subjectively and/or the stressors you face, over time, by all means, that is a useful way to use the data**. It could be that in your case the inputs and weights used by the algorithms reflect well your responses.

Note that even in these cases, **you are taking a very reactive approach** to life (i.e. respond to any acute change, with little or no focus at all over the long-term picture, which might be a questionable approach regardless of our interest in training). **A better way would be to have a plan and use wearables measurements** (i.e. resting physiology) **to capture how you are responding to such a plan, potentially making adjustments** (see also [this blog](https://marcoaltini.substack.com/p/how-to-include-heart-rate-variability), in the context of training).

Always start with a plan.

Here are some examples of estimates, and why they can only be approximate guesses:

- **Sleep time** : movement and autonomic activity (heart rate, HRV), temperature, cannot capture with certainty the difference between being asleep and awake. In particular, simply not moving while being relaxed (low heart rate) causes wearables to often get bedtime wrong, as many have experienced. Devices that have been out there for more than a decade, continuously improved and fine-tuned, get sleep time off by more than an hour (see[here](https://www.sciencedirect.com/science/article/abs/pii/S2352648323000466) ), what’s the point?
- **Sleep stages** : changes in autonomic activity and other parameters can somewhat follow changes in brain activity during different sleep stages. However, without measuring brain waves, eye movement, and muscle activity, the error remains large. While at the population level, we might get an idea of different patterns, an individual cannot determine with high accuracy how much time is spent in different sleep stages using this method.
- **SPO2** : oxygen saturation is in part measured, as sensors are used to capture blood volume changes at different wavelengths. However, once this measurement is done, the data is used to empirically determine SPO2 based on a previously collected dataset mapping the various parameters, making this estimate highly dependent on that original dataset (who was included, their skin tone, health status, etc.).
- **Calories** : calories are estimated using movement data, and sometimes movement is combined with heart rate. In either case, the estimate can very easily go wrong: activity type, more than level of motion, determines caloric expenditure, especially when the wearable is far from the body’s center of mass (i.e. in all cases, as these are not worn at the hip). Heart rate is also flawed, as the relationship between heart rate and caloric expenditure is individual, with heart rate changing based on e.g. cardiorespiratory fitness level, in ways that do not impact caloric expenditure (and this would even assume that the wearable can measure heart rate correctly). The same applies to made-up metrics that are just rebranding of calories, e.g. strain.
- **Continuous “stress” estimates:** apart from the technological issues here (i.e. HRV cannot be captured unless there is absolutely no movement, not even typing on a keyboard would work for a wrist or finger wearable), the physiology of heart rhythm modulation highlights how incorrect is the assumption that stress is the main factor behind changes in heart rhythm during the day (e.g. if you just drink some water, your HRV increases, if you eat, it decreases, because of digestion, while parasympathetic activity is actually higher, which means that HRV has no relation with stress responses most of the time during the day. Let alone that swallowing saliva, something we do between 18 and 400 times for hours, drastically increases HRV acutely and again has nothing to do with stress - it us just an artifact). On top of these issues, your body’s response to a stressor, e.g. exercise, is not something you want to avoid, which is what you’d end up doing when listening to naive oversimplifications provided by a wearable (e.g. your heart rate is high, you must be stressed, which must be bad, while in fact, you might have just exercised, which will bring long term benefits to your health). See[this blog](https://marcoaltini.substack.com/p/a-quick-note-on-continuous-heart) for a discussion of this topic. The only goal of continuous stress estimates is to keep you “engaged” with the device and app while missing the point entirely about how the body works and measuring stress following a proper protocol.

What estimates can you trust then? In my opinion, none is good enough for actionability. **I do not look at any wearable-derived estimate for decision-making and I would not recommend any athlete or coach to do so**. 

If you are wearing a sensor 24/7 and this sensor cannot detect your bedtime accurately because you are reading in bed, then what are you wearing it for? (I hate to say it but there is no way you can detect any sleep-related parameter with high accuracy without measuring brain waves).

**I have seen elite athletes and coaches doing an intervention and then looking at how much it would impact wearable-derived REM sleep, then deciding the best course of action from there**. This is absolute nonsense. Please do not waste your time and energy this way. **No wearable can provide you with data anywhere near the accuracy you would need to evaluate such an intervention.** 

Here I am not even touching on other big issues with estimates, i.e. that the algorithm might change all the time and you might not even know. This is unlikely to happen with measurements.

If you are serious about using wearables’ data to understand how the body is responding to an intervention (or simply to training or life in general), please focus on measurements, not on estimates, and certainly not on estimates of unknown parameters (i.e. the made-up scores).

See also:

# Tracking considerations

**The holistic view (provided by a wearable) is a myth**. A wearable has no idea for example of muscle soreness and context (is your heart rate high simply because you are having a good time with a bunch of friends or are you stressed - whatever that means?). 

My recommendation is to take a step back and don’t get too captured by the idea of continuous tracking, or tracking “everything in the same place” as something inherently useful.

**For any athlete, muscle soreness is one of the key limiters**, and yet **no wearable is of any use when it comes to it**. If anything, this simple consideration should get you to **take the whole device or company rhetoric a bit less seriously**: a great deal of the picture is not there even if you wear it all the time. 

Not only the wearable or app is missing information, but **aggregating information gives the false expectation that the data becomes somewhat more insightful, while it is simply diluting the insight**.

In my opinion, looking at actual physiological data and how it [deviates from your normal](https://marcoaltini.substack.com/p/whats-your-normal-range-for-heart), and contextualizing such data with your subjective feeling, training data, etc. separately can be more helpful. This approach also allows you to use the wearable for what it can do better: measuring resting physiology, ignoring measurements during activity, estimates, made-up scores, etc.

It is absurd to think that by using a wearable 24/7 (even while you charge it, wonderful) you get the full picture. Wear it when you need it to collect high-quality measurements that are actionable (i.e. resting physiology when you sleep), otherwise don’t bother.

This is the beauty of resting physiology (e.g. resting heart rate and HRV): as an overall marker of stress, you do not need to be able to quantify all sorts of things to understand how your body is responding. Resting physiology (e.g. **HRV**) **already reflects how you are responding to whatever you do**. - while collecting more data does not add actionable information, [quite the contrary](https://marcoaltini.substack.com/p/a-quick-note-on-continuous-heart). 

**Good sensors and good protocols beat "more data and machine learning" any day.**

# Wrap-up

In this blog, I have tried to provide an overview of how and when the different metrics reported by today’s wearables are derived. Some are measured, others are estimated, some are estimates of known parameters and others of unknown or made-up parameters.

**Given issues with measurements outside of complete rest, and how errors compound in many estimates, as well as how mixing physiology and behavior eventually confounds the body’s responses, my recommendation is to spend your time and energies on the few parameters that can be actually measured**. Minimize error (e.g. looking at resting data) and maximize physiological meaning (e.g. looking at night data or data collected first thing in the morning). 

Much of what I have discussed above was triggered by seeing elite tennis players during competitions using wearables. It made no sense, for the reasons explained here: measurements of heart rate would be inaccurate, measurements of resting physiology (e.g. night heart rate or HRV) are not impacted by data collected (or not collected) during the day, estimates of unknown parameters should have no place in an athlete’s life (i.e. readiness or recovery scores, strain, etc.).

I am obviously in favor of using wearables, but it should be clear from the above, that **the only meaningful thing to do is to wear your device when you sleep, to get an accurate measurement of your resting physiology, and then leave the wearable on the night table**. I get it that they are designed for you to wear them all the time, but if you are interested in using them for what they can do well, then this is the way it is. Minimizing the metrics obtained might be a useful side effect, not to drown in data. 

Keep in mind that it’s not all good or all bad.

**Ask yourself:**

**is the parameter I am interested in actually measured by this device, or is it estimated?**

if it is estimated, **what is the degree of error?** Can I find a validation? If not, **when using multiple wearables to look at this specific parameter, are results consistent?**

What matters is that we understand what can be trusted more and what can be trusted less:

measurements (heart rate at rest, night HRV) > estimates of known parameters (sleep time, stages) > estimates of unknown parameters (readiness or recovery scores, sleep quality, etc.).

This way, we are not fooled by these devices, nor do we dismiss them when they can actually be useful.

I hope this was informative, and thank you for reading!

# **Ways to Show Your Support**

No paywalls here. All my content is and will remain free.

If you already use the [HRV4Training](https://hrv4training.com/) app, the best way to support my work is to sign up for [HRV4Training Pro](https://hrv4training.web.app/).  

Thank you!

# **Endurance Coaching for Runners**

**If you are interested in working with me**, please learn more [here](https://marcoaltini.substack.com/p/coachcorner-my-training-philosophy), and fill in the athlete intake form, [here](https://docs.google.com/forms/d/1X-deb1EQCa7t4eO-zxllEIR3LO-g6HBeiB97vdX2rMM/edit).

Marco holds a PhD cum laude in applied machine learning, a M.Sc. cum laude in computer science engineering, and a M.Sc. cum laude in human movement sciences and high-performance coaching.

He [has published](https://www.researchgate.net/profile/Marco_Altini?source=post_page---------------------------) more than 50 papers and patents at the intersection between physiology, health, technology, and human performance.

He is co-founder of [HRV4Training](https://www.hrv4training.com/), advisor at Oura, guest lecturer at VU Amsterdam, and editor for IEEE Pervasive Computing Magazine. He [loves running](https://www.strava.com/athletes/12073735?source=post_page---------------------------).

Social: