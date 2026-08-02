---
title: "The Best Way to Get Things Done"
author: "Nick Maggiulli"
publication: "Of Dollars And Data"
published: 2024-03-19
saved: 2024-04-04T00:00:00+00:00
created: 2024-04-04T00:00:00+00:00
source: "https://ofdollarsanddata.com/the-best-way-to-get-things-done/"
estimated_pages: 9
status: incomplete
draft: true
tags: []
---

In today’s fast-paced environment, it can feel like there’s never enough time to accomplish all of our goals. Between career obligations, socializing with friends and family, and our own personal development, optimizing how we use our time seems to be the challenge of the 21st century.

I am no productivity guru, but I’ve spent a considerable amount of time studying how people get things done and how people manage their time. Unfortunately, I haven’t found a silver bullet. There is no single way that will allow you to get more done overnight.

However, there are a few frameworks I’ve found that can start moving you in the right direction. It might seem odd that I am talking about productivity on a financial blog, but I believe that [your income is the most important component of your financial success](https://ofdollarsanddata.com/paychecks-not-portfolios/). And, if you want more income, increasing your productivity is one of the best ways to have more career success and, ideally, more income.

With that being said, let’s think about how you get through your to-do list.

## How Do You Get Through Your To Do List?

Imagine you are a financial advisor that comes into the office on a Monday morning with the following to do list:

- Call back a client related to a question about their financial plan
- Setup a meeting with a prospect
- Create content to market your services on social media
- Spend 1 hour doing continuing education on an investment-related topic

Which of these items should you do first? Should you do the one that takes the least amount of time, the one that’s the most important, or the one that is most likely to increase this year’s profits?

Whatever you choose, this class of problem falls under the what is known as [scheduling theory](https://encyclopediaofmath.org/wiki/Scheduling_theory), or the science of finding the optimal order to do a given set of tasks. Though you may have never heard of scheduling theory before, I know you know the concept well. We all must make decisions under uncertainty based on what we have to do at any given moment. This is why the study of how to get things done (aka scheduling theory) is so important.

There’s good news and bad news about scheduling theory. The good news is that for some set of tasks, there is an optimal solution for which order you complete them in. However, the bad news is that this isn’t true for all sets of tasks.

Some scheduling problems have no optimal solution. These problems are what computer scientists call “intractable.” How many scheduling problems are intractable? The vast majority. As Brian Christian and Tom Griffiths stated in [Algorithms to Live By](https://amzn.to/49kyQLh):

Of the 93% of problems that we do understand, however, the news isn’t great: only 9% of them can be solved efficiently, and the other 84% have proven intractable. In other words, most scheduling problems admit no ready solution. If trying to perfectly manage your calendar feels overwhelming, maybe that’s because it actually is.


Note that this 84% intractable figure includes the set of problems that involve multiple individuals completing tasks in a team setting. When you remove those, the figure that is intractable (for an individual completing a set of tasks) isn’t quite so high.

But, before you get discouraged, keep in mind that many sets of tasks still have an optimal solution if you follow the right strategy. Let’s look at some of those now.

## Which Scheduling Strategies Are Out There?

When it comes to figuring out the ideal order to complete a set of tasks, there are a few different strategies you can employ:

- **First Come, First Serve:** This strategy involves completing your tasks in the order you receive them. No emphasis is placed on a task’s due date, importance, or expected completion time.
  - Pros: Fairness (tasks are completed in the order received).
  - Cons: Slow and Doesn’t Prioritize (some tasks can take a long time and some can be missed altogether).
- **Earliest Due Date:** This strategy involves completing the task with the earliest due date first and then going on to the next one. No emphasis is placed on when a task is received, it’s importance, or it’s expected completion time.
  - Pros: Prompt (prevents tasks from being completed late)
  - Cons: Doesn’t Prioritize (important tasks may not get the attention they deserve)
- **Priority Scheduling (Highest to Lowest):** This strategy involves focusing on the highest priority tasks first, then moving down the list. No emphasis is placed on when a task is received or it’s expected completion time.
  - Pros: Prioritizes (cares about a task’s importance)
  - Cons: Slow (can leave quicker tasks longer in the queue than necessary)
- **Shortest Processing Time:** This involves completing tasks based solely on how long they take to finish. While this will minimize the size of someone’s task list, it also de-emphasizes the importance and priority of tasks.
  - Pros: Fast, High Throughput (completes more tasks in less time)
  - Cons: Doesn’t Prioritize (can miss tasks and not emphasize important tasks). Heavier Mental Load (this strategy requires the ability to switch in and out of different tasks quickly, which is not ideal for everyone.)
- **Weighted Shortest Processing Time:**  Similar to the shortest processing time strategy, this strategy completes tasks based on how long they take to finish, but changes the ordering of the tasks based on their importance. For example, imagine three tasks with the following expected completion times:
  - Task A (20 minutes)
  - Task B (2 minutes)
  - Task C (60 minutes)
- The Shortest Processing Time strategy would tell you to do Task B, then Task A, and, finally, Task C. But what if we could include weights (1-10) on these tasks based on their relative importance? Let’s assume the following weights for each task:
  - Task A (20 minutes), Weight = 2
  - Task B (2 minutes), Weight = 1
  - Task C (60 minutes), Weight = 8
- Now if we divide the weight by the expected time to complete the task we would get:
  - Task A = 2/20 = 0.1
  - Task B = 1/2 = 0.5
  - Task C = 8/60 = 0.13
- Using this new weighted measure, the Weighted Shortest Processing Time strategy would tell you to do Task B, then Task C, and, finally, Task A. Since Task C is 4x as important as Task A, it is prioritized though it will take 3x as long to complete.
  - Pros: Generally Fast, Prioritizes (Gets more tasks done and cares about a task’s importance)
  - Cons: Higher Ongoing Costs (takes more time to organize task list as you must weight and then re-order the items on the list as new tasks are added)
- Though the Weighted Shortest Processing Time strategy will take you a bit longer to organize, it also might just be the best scheduling strategy out there. Once again from [Algorithms to Live By](https://amzn.to/49kyQLh) :

In fact, the weighted version of Shortest Processing Time is a pretty good candidate for the best all-purpose scheduling strategy in the face of uncertainty.


Though the Weighted Shortest Processing Time strategy is great to use, how do you know if it’s right for you? For this we turn to our next section.

## Which Scheduling Strategy is Right For You?

Finding the right task completion strategy is something that is very dependent on the context of your work. If you’re an air traffic controller, minimizing the number of incomplete tasks (e.g. cancelled flights) is probably more important than aiming for the shortest completion time (e.g. minimizing delays). However, if you work in a hospital, emphasizing priority (e.g. a patient with no heartbeat) is more important than the number of procedures you complete in a day.

Every industry and every job has a different value system that they apply to their tasks. **Once you know the value system you are working under, then it becomes much easier to pick the right strategy for getting things done.**

A great example of this comes from Matthias Lux, a data scientist at Uber, [who wrote about](https://www.uber.com/blog/analyzing-experiment-outcomes/) how Uber had to look beyond the *average* outcome when evaluating new algorithms that would match riders with drivers. Matching riders with drivers is a kind of scheduling problem since each rider can be thought of as a task (with a wait time) that needs to be completed by the driver.

How should Uber allocate their drivers to riders? A simple solution is to find a strategy that leads to the lowest *average* wait time. This seems great at first glance, until you realize how it might impact someone living in a less visited location. If you create an algorithm that directs all of your drivers toward riders in the most populated parts of a city, this will decrease the *average* wait time across the system, but will also increase the wait time for a small number of riders in remote areas.

Uber could find this acceptable, or it could not, depending on its goals. If it wants as many riders as possible on the platform, then increasing wait time by 2 minutes for those in downtown might be worth it if it also decreases wait time by 10 minutes for those on the outskirts of the city.

Either way, everything comes back to what goals you are trying to accomplish. Once you define your goals, then you can determine which scheduling strategy is right for your situation.

Now that we’ve discussed which strategy might be right for you, let’s wrap things up by considering why higher productivity isn’t always the ideal solution.

## When Getting More Done Isn’t Actually the Answer

An implicit assumption I’ve made throughout this post is that getting more done is always the right answer to your problems. But, it may not be.

In [Four Thousand Weeks: Time Management for Mortals](https://amzn.to/3SintN6), Oliver Burkeman argues that the real solution to getting more done is accepting that you won’t get everything done. Instead, Burkeman believes that we should focus on getting *the most meaningful things done* instead of getting everything done. As Burkeman states:

I’ve been writing as if the efficiency trap were a simple matter of quantity: you have too much to do, so you try to fit more in, but the ironic result is that you end up with more to do. The worst aspect of the trap though, is that it’s also a matter of quality. The harder you struggle to fit everything in, the more time you’ll find yourself spending on the least meaningful things…If you never stop to ask yourself if the sacrifice is worth it, your days will automatically begin to fill not just with more things, but more trivial or tedious things, because they’ve never had to clear hurdle of being judged more important than something else.

Commonly, these will be things other people want you to do to make *their* lives easier, and, which you didn’t think to try and resist. The more efficient you get, the more you become “a limitless reservoir for other peoples’ expectations,” in the words of management expert Jim Benson. 


As one of my mentors told me early in my career, “The reward for work is more work.”

My solution to this problem takes it a bit further than Burkeman. Not only should you prioritize the right things, but you should also ensure that there’s always some slack in the system. In other words, make sure you’re almost never fully utilized. Why?

Because when you’re already at 100% of your operating capacity and an unexpected emergency hits, the whole system fails. You’ve probably felt this feeling before. It’s overwhelming and you can’t figure out what to do next. It’s the same thing that happens to your computer when you have too many programs open. It doesn’t know which program to prioritize, so it freezes, and then crashes.

The same thing happens with people when we get too busy. We don’t know what to do and we can crash. Unfortunately, that single crash can decrease productivity more than a slow day once in a while. That’s why your goal should be to be about 80%-85% utilized. You may have a less productive day here or there, but this slight inefficiency will prevent larger failures when fires inevitably pop up from time to time. I firmly believe this is one of the reasons why I haven’t burned out despite working full-time and blogging every single week for over 7 years now.

My secret to getting so much done is rarely operating at full capacity. My philosophy on this is simple—if you take care of the days, the years take care of themselves.

We know that this is right intrinsically, but many of us choose to ignore it to our own detriment. If I told a runner to sprint at 100% effort, they might be able to sprint for a minute before they would have to slow down or stop completely. But, if told them to run at 75% of their max effort, they could go on for hours. Same person. Same body. The only difference is what capacity they are operating at.

So instead of trying to get everything done, the better solution is to get the right things done (at the right capacity). But figuring out what the right things are is a challenge all its own.

If you enjoyed this post, check out [Algorithms to Live By](https://amzn.to/49kyQLh) and [Four Thousand Weeks](https://amzn.to/3SintN6), two books I highly recommend on this topic. Thank you for reading!

**If you liked this post, consider [signing up for my newsletter](https://ofdollarsanddata.com/newsletter/).**

This is post 390. Any code I have related to this post can be found here with the same numbering: [https://github.com/nmaggiulli/of-dollars-and-data](https://href.li/?https://github.com/nmaggiulli/of-dollars-and-data)