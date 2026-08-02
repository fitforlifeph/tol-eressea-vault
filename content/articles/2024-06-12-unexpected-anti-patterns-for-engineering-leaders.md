---
title: "Unexpected Anti-Patterns for Engineering Leaders"
author: "First Round Staff"
publication: "First Round"
published: 2024-05-30
saved: 2024-06-12T06:48:45.803410+00:00
created: 2024-06-12T06:48:45.803410+00:00
source: "https://review.firstround.com/unexpected-anti-patterns-for-engineering-leaders-lessons-from-stripe-uber-carta/"
estimated_pages: 21
status: complete
draft: false
pdf_url: "https://archive.javierpgomez.com/articles/2024-06-12-unexpected-anti-patterns-for-engineering-leaders.pdf"
tags: []
---

Whenever [**__Will Larson__**](https://www.linkedin.com/in/will-larson-a44b543/?ref=review.firstround.com) meets up with fellow CTOs or heads of engineering at other startups, he often finds himself having the same conversation over and over again — an engineering leader’s version of Groundhog Day. The biggest challenge these leaders are facing is pressure from their CEOs to drive engineering velocity. The message is usually: ship more value, more quickly. “The problem is that no one has a whole lot of conviction that there is a simple way to do this,” says Larson.

“There's no lever like there is in sales. I think this is not totally true in sales either, by the way, but if you talk to people, there's the theory that in sales, you could just add more people and more sales will happen,” he says. “People look at recruiting the same way. ‘If we do five hires per quarter per recruiter, we just need to add two more recruiters and we’ll be hitting our targets.’”

However, engineering leaders will be hard-pressed to find a similar lever to pull. “For engineering, there are just no measures that I find super helpful here. There are teams where one individual may be pulling a ton of weight,” he says. “Then there are teams that have one individual who might be getting in the way and creating conflict, and the rest of the team can’t move forward unless they’re removed.”

But Larson’s keenly aware of how this predicament sounds to non-technical leaders. “Engineering leaders, especially at large companies, are managing a team of a couple hundred people. That team might cost $50 to 100 million in salary a year. So as a CEO, when you hear from your eng leaders that ‘Engineering is an art, and you can’t predict how it’s going to work,’ it’s frustrating. They’re sitting there thinking, ‘They’re telling me this is art, but I’m spending $100 million on this art each year.’ That’s not reassuring.”

As the CTO at [**__Carta__**](https://www.carta.com/?ref=review.firstround.com), Larson is no stranger to the intricate challenges like these that engineering leaders wrestle with on a daily basis. His winding career has landed him in leadership roles at **Stripe**, **Uber** and **Calm** (also in the CTO seat) — and he’s scaled engineering teams from tens to hundreds of people. 

As he’s teased out lessons from his own experiences, he’s become a go-to resource for many, penning several highly-circulated essays on his ever-excellent engineering blog, [__Irrational Exuberance__](https://lethain.com/?ref=review.firstround.com), and three books. His latest, [__An Engineering Executive’s Primer,__](https://www.amazon.com/Engineering-Executives-Primer-Will-Larson-ebook/dp/B0CV4QGPXD/?_encoding=UTF8&pd_rd_w=mgGna&content-id=amzn1.sym.cf86ec3a-68a6-43e9-8115-04171136930a&pf_rd_p=cf86ec3a-68a6-43e9-8115-04171136930a&pf_rd_r=131-3454494-9143647&pd_rd_wg=GqqH7&pd_rd_r=8ce3dba2-a0e0-438a-ad35-f210dc21e1a3&ref_=aufs_ap_sc_dsk&ref=review.firstround.com) hit the shelves last year. (Larson has also shared his wisdom right here on the Review before, unpacking [__his highly practical framework on the optimal size and state of engineering teams__](https://review.firstround.com/how-to-size-and-assess-teams-from-an-eng-lead-at-stripe-uber-and-digg/).) 

Across his work, Larson has consistently seen that this misalignment between eng leaders and other executives stems from a lack of flexibility. As he sees it, too many well-meaning engineering leaders go by the book of conventional leadership advice.

**"Anytime you apply a rule too universally, it turns into an anti-pattern,”** Larson says. In other words, once a practice is labeled as generally helpful or unhelpful, it blinds leaders to how that practice would work in the context of *their* organization. The key to effective engineering leadership, Larson argues, lies in figuring out *which* scenarios are worth deliberately defying conventional logic, and when to simply follow the rules. 

We have to have the openness to think through whether a different approach might make sense in a very specific case. That’s a fundamental part of engineering.

[__In this exclusive interview,__](https://review.firstround.com/podcast/a-masterclass-in-engineering-leadership-from-carta-stripe-uber-and-calm-will-larson-cto-at-carta/) Larson lays out **three commonplace engineering leadership practices that he thinks have become anti-patterns.** First, he argues the case against always avoiding micromanagement, providing two concrete tactics leaders can use to get closer to the details. Next up, he explores why measuring an imperfect metric isn’t the worst-case scenario. He wraps with a thought-provoking reflection on why leaders shouldn’t be umbrellas for their teams, and how they can strike the right balance between management by committee and unwieldy bottoms-up decision-making.

Sprinkled throughout are anecdotes from managing teams at Stripe, Uber, Carta and Calm, full of contrarian thinking meant to push engineering leaders out of their comfort zones. But his advice extends far beyond engineering. Startup leaders in any function will find new tactics and frameworks to apply to their own strategy, and CEOs and founders might just find a new perspective when managing their eng leaders. Let’s begin.

## **Unexpected Anti-Pattern #1: Shying Away from Micromanagement** 

To start, Larson maps out what skills make the top 1% of engineering execs stand out from the top 50%. “The core challenge for engineering execs is they have to wear three different, kind of opposing hats. The best ones can toggle back and forth between them deftly.” He lays out the opposing goals for each “hat:”

- **Executive team member.** Finding ways to drive the business forward. “Sometimes that means making decisions that are ‘bad for engineering overall,’ like reducing the engineering budget, for example. Or moving to a business unit model where there is less engineering voice in the room on certain topics,” Larson says.
- **Engineering manager.** Figuring out the structure of policies needed to run the engineering org, and how to be an effective people leader.
- **Engineer.** Keeping the bar for technical excellence high. “You’re still responsible for the technical excellence and execution of engineering, despite any outside stressors,” Larson says.

“I find a lot of executives tend to lean a little bit too heavily on one of these dimensions,” he says. But a common denominator lurks in all three of these roles that keep execs from excelling to the engineering leadership hall of fame. No matter which hat they’re wearing, leaders stumble when they carry over management practices that no longer serve them. 

“Typically when you first start managing, you're coming from a functional expertise role, like a staff engineer or the tech lead for a team. Then all of a sudden you become the manager for that team. So you're in an interesting place where you have the most context technically about everything the team is doing, but you're also now the people manager,” Larson says.

“Now you have the authority to set work and tell people what to do. At that moment, the advice that people constantly get is to step away from the details. You are told to step away from the code because staying involved will make you a bad manager,” he says.

For some people, he recognizes that this can be helpful advice. Folks who are extremely particular about the way they want things done [__*should* let go of the reins__](https://review.firstround.com/give-away-your-legos-and-other-commandments-for-scaling-startups/) and let their teams make decisions on their own. But the vast majority of engineering managers who turn into execs, follow this advice to their detriment. “**One of the biggest lessons in management over the last decade is that micromanagement is bad. But I think this is an anti-pattern**, **because it creates disengaged and context-free leadership**, and leadership can be so much more than that,” he says. 

“Too many executives take this kernel of advice and as they grow more senior, start to think of themselves only as resource allocators — that their main job is to allocate budgets to different teams and periodically check in on the quality. While that’s certainly an important part of management, that’s not the entirety of it,” Larson says.

New engineering managers are often advised to “step away from the code.” But an extremely high-functioning exec understands the domain they are operating in at some level of detail. As you get too far out of the details, you just become a bureaucrat. Too many well-meaning engineering managers end up as bureaucrats.  

Larson urges engineering execs to forget the term micromanagement altogether and focus instead on cultivating [__a different set of leadership styles__](https://lethain.com/developing-leadership-styles/?ref=review.firstround.com) they can pick from. “In cases where there are no clear paths forward or where the folks who have the context around the path forward are violently in disagreement, it pays to get into the details and make the decision yourself,” he says. “That way, you can understand the levers that could really transform the business, the outcomes your team needs to accomplish, the time frame to do it in and how it serves your users better.”  

Developing a stronger conviction around your [__decision-making__](https://review.firstround.com/the-6-decision-making-frameworks-that-help-startup-leaders-tackle-tough-calls/) is a career-long practice and one that Larson is still working on himself. “Asking questions like ‘What are we doing? Why are we doing it? What’s the data? Where is the actual source of data?’ monthly or quarterly help me drill further into the details,” he says.  

But if you are looking for more tactical ways to zoom in as a manager or exec, Larson also unpacks two tried-and-tested tactics that will bring engineering leaders closer to the details:

### **1. Get up to speed by “conflict mining”**

“**The number one way that I see new engineering leaders struggle when they come into a new place is that they assume the context from their previous company applies as is**,” says Larson. 

This tends to happen most [__when leaders transition from large to small organizations__](https://review.firstround.com/how-to-scale-yourself-down-not-up-as-a-leader/), but missing even small contextual details in a new environment has the potential to damage the success of the operation. 

Larson has tripped over this hurdle himself. “One of the challenges we had on Uber’s infrastructure team back in 2014 is that teams were spinning up new services, and a new kind of function code almost every week,” he says. “We were supposed to help them provision these new services. From the very first week, I started to realize my team was further behind every week than when they started. So, my first week there, we were two weeks behind, my tenth week there, we were four weeks behind, and we were just getting worse.”

As a solution, Larson’s team went down a path of creating self-service provisioning and automation tooling that made it possible for anyone at the company to spin up a new service themselves. “We felt really good about that. We were at the forefront of a movement of many companies doing that,” Larson says.

“Then I came to Stripe and I saw the same problem. Teams were feeling stuck. I wanted to employ the same solution,” he says. “But I had just started, so I wanted to talk to a bunch of the senior engineers about the idea first and say ‘Hey, here's what we did at Uber. I think we should do it here too.’”

Larson calls this the **“mining for conflict”** stage of getting up to speed in a new role, and it’s one of his favorite tactics to deploy as a senior engineering leader starting fresh in a new company to get closer to the details, even if it means long conversations with folks with opposing viewpoints.

“One of Stripe’s most senior engineers absolutely hated my automated tooling idea,” Larson says. “I kept trying to pitch him though. I remember one conversation we had where I asked him, ‘What could I tell you about this idea for you to be comfortable with us trying it out?’ His response was that there was nothing I could tell him. He’d never be on board. At first, I thought, ‘This is a really unreasonable person.’ But later as I dug into it, I discovered he was right. How Stripe did technology was pretty different from Uber. One of the core undocumented strategies at Stripe was they used a Ruby monolith, and so everything was done in the Ruby programming language with a few minor exceptions. The way I wanted to approach this problem wasn't aligned with that.”

This process of conflict mining served Larson a key lesson. “I could have just ignored him, But then I would have missed the key learning, which is that *I* was the one who was missing context, and needed to refine my approach.” 

Things are not the same across companies, and you can figure that out pretty quickly by finding something controversial and testing for conflict. The wrong way to solve this is to actually implement the conflict-heavy thing. The right way to do it is just to go have a bunch of conversations.

Another example happened when Larson was at Calm — which scaled from five engineers to over 100 under his leadership. He ended up making the tough call to cancel a major product migration from the monolith to a multi-product suite.

“When I got to Carta, I had the instinct to do the exact same thing,” says Larson. “I thought, ‘If it worked at Calm, why wouldn’t it work here?’ But I had to test that idea and get sped up on the context and everyone else's perspectives.”

It’s key to not confine your conflict mining strategy to your peer group on the leadership team. . “You can usually get buy-in from other executives pretty easily, but it’s much more difficult to get buy-in from people with the most context around a given problem,” he says, “Their opinion is most valuable because they are the ones who live in the details. You can’t lie to them. They know the truth of how things run.”

Successful leaders come in and ask, ‘How can I change myself to fit?’ not ‘How can I force my entire organization to fit to work with me?’ It's hard to move organizations, and you shouldn't do it if you don’t need to.

### **2. Write the details down**

Any executive who has come in fresh to a new company, no matter the size or industry, will probably be familiar with the following scenario: “Every company you come into, you’ll start asking around and the engineers will say, ‘There's no product strategy,’ Then you turn around and go to the product managers and they'll say things like, ‘There's no business strategy.’ Then you go back to the engineers, and they say ‘There’s not even a technology strategy written. What sort of company are we?’” Larson says. “**What ends up happening is that senior leaders coming in will just assume that their last company’s strategy will apply because nothing is written down that would say otherwise**.” (His transition from Uber to Stripe which he details above is a prime example.) 

There’s this pervasive belief that there’s no strategy anywhere, but that’s not true. There is strategy everywhere, it’s just rarely written. 

Complicating things even further, Larson also has found that many companies do have a habit of writing things down, they just aren’t the *right* things. “It’s the small decisions that end up getting documented,” Larson says. “You’d think it would be the opposite, but in my experience, the answers to important questions like, ‘Why did we go into this business? Why are we shutting down this business line? Why are we doing this services migration that's going to take five years?’ literally aren't written down anywhere.” 

[__Building a culture of documentation is essential__](https://review.firstround.com/investing-in-internal-documentation-a-brick-by-brick-guide-for-startups/) to unlocking a fast-moving engineering org, and most leaders and companies do seem to have a good grasp on this. However existing leaders are often faced with a ton of inertia. “Where there’s already momentum, it’s particularly hard to course correct on large things,” Larson says. “It takes much more activation energy than continuing down the path they were already on.” 

So for those new leaders coming into a company, they have a unique opportunity to create a lot of [__impact in their first 90 days__](https://www.lennysnewsletter.com/p/how-to-make-an-impact-in-your-first?ref=review.firstround.com) just by coming in with fresh eyes. Larson stresses that before leaders jump the gun and start to etch their own strategies into stone, it’s important to consider these two pieces of advice: 

- **1. Get your shovel and go digging.** Understand the*why* behind every decision made. “Sometimes the underlying context or beliefs about something is no longer true, but people continue going down that path because they haven’t stepped back,” Larson says. “So it’s up to you to do some archeological digging to figure out the rationale.” He suggests having as many conversations with longtime employees as possible. “From that you can figure out if the underlying beliefs are still true,” he says.
- **2. Use other companies' success as benchmarks.** “Sometimes the decision-making is good, but three years in, the execution is still not working. The easiest way to get a sense of what is real and what’s not, especially for new leaders coming in, is by looking at examples of progress at other companies. See how long it took Airbnb or Dropbox to accomplish the same task and set it as a benchmark,” says Larson. “It might not be a perfect truth, but it gives you a reasonable guess. If you are taking three times longer than them, and still haven’t gotten any meaningful complexity moved out of your monolith, then it’s fundamentally not working and time to have some challenging conversations.”

After thoroughly investigating everything that’s already happened, combined with fresh benchmarks and goals to reach, now it’s time to actually put pen to paper. If you’re a leader who’s staring down a blank strategy doc, Larson recommends starting with Richard Rumelt’s “[__good strategy, bad strategy” framework__](https://www.amazon.com/Good-Strategy-Bad-Difference-Matters/dp/0307886239?ref=review.firstround.com) as an outline. 

“Rumelt believes that each business decision should be explained in a way that answers three questions,” Larson says. He walks through how an imaginary startup would frame its answers when figuring out a cost strategy:

- **What’s the diagnosis?**  The first thing you should do is codify the reality of the circumstances you are working in. Rumuelt calls this a diagnosis. “For example, a diagnosis could be that it’s 2024 and funding is really hard to get. We have $10 million in the bank and spent about $2.5 million last year. Our revenue is steady, but it's not growing. That’s our diagnosis.” Larson says.
- **What are the guiding policies?** Next, intercept your diagnosis and turn it into an approach to deal with the problems at hand with guiding policies. “Strong guiding policies include parameters for both how decisions are going to get made and what the goals of those decisions are,” Larson says.“So in our example, as long as costs are kept flat year over year and the startup maintains its current revenue, we’ll have four years of runway, and we’re comfortable with that. So we plan to spend $2.5 million. We also will aggressively prevent any initiative that's going to cause us to spend more money,” he says.
- **What’s the coherent action?** “Rumelt's biggest concern about strategy is that it consists of a lot of spoken words that don't actually get implemented or used anywhere. So he has this idea of coherent action, which says a strategy is only real if you are specifically doing something today, based on the guiding policies to make that a real thing. An example could be a monthly meeting with finance to review every expenditure. If you start seeing an increase in the curve, you can immediately spot the fix to get back on track,” he says.

Each point should be detailed enough to give the full picture, but concise enough to get across a clear message. One last point to consider is documenting your beliefs on technology investment and how broad you want your investment to be.

“Do you want to have one programming language for everything? Or do you want to pick the best programming language for each problem that you work on?” Larson says. “Uber was more in the latter half-camp of supporting many things. Stripe leaned toward having one tool for all problems. When that’s written down and codified somewhere, it can help inform your conviction in making decisions in the future.”

If you just write things down, no matter how bad they are, your strategy will improve almost overnight. If you don’t write things down, it’s impossible to improve your strategy. 

## **UNEXPECTED ANTI-PATTERN #2: PUSHING BACK ON MEASURING FLAWED METRICS**  

“[__Measurement__](https://lethain.com/measuring-engineering-organizations/?ref=review.firstround.com) is ripe with anti-patterns,” says Larson. Like many engineers, earlier in his career, Larson was a self-described “purist” when it came to finding and measuring the right thing to anchor his team’s strategy around. “What I found is that 1) This took forever and 2) You can’t guide people to the perfect thing if they don’t have the context of why the earlier, simpler measures didn’t make sense,” he says. 

Only after spending time in several leadership roles did Larson realize that **getting caught up on finding the right measurement *was* the anti-pattern**. “Often when people start measuring, there's always a concern that their measurement is flawed. And that's true for all functions,” he says. “But I’m a believer in measuring something imperfect, but useful, versus holding out for the perfect metric while measuring nothing in the interim.” 

You can be ideologically pure and say we shouldn't measure something, but all that does is slow down the learning of the organization around you. It doesn't actually help you accomplish your goal. 

He gives a simple example of using story points as a success metric. “Everyone you talk to about story points in a sprint is going to say this is a terrible way to measure velocity, it’s a waste of time,” he says. “And that may be true, but if your CEO disagrees with that, then that’s actually interesting, right? Because it means that they haven't built an intuition about how these things work.”

Instead, he says engineering leaders are better off helping their CEO build an intuition in this area. “That only happens by actually measuring story points, reporting to them and then getting into the details of why it’s not a useful metric to show velocity,” he says.

I’m coming to appreciate that the most valuable thing you can do as an engineering exec is to educate other execs on how engineering works, instead of shielding your org from everyone else.

The ultimate goal when it comes to laying out the measurements in your eng strategy isn’t getting into the weeds of a debate over whether reliability more accurately measures the progress of your team then, say, the volume of pull requests. Instead, Larson says engineering leaders should place a premium on how much their CEO absorbs. “Remember, measurements are going to change every quarter, for the rest of time at your company,” Larson says. “So the real goal when you measure upwards is how much does your CEO understand the real substance of the work your team is getting done?”

In this section, Larson offers up two ways engineering executives can prioritize context and alignment with their CEO and wider leadership team:

### Focus on improving mental models

Early on at Stripe, Larson’s team implemented a controversial metric to track his team’s success: reliability. It started by tracking uptime for their enterprise customers (“If we dipped below four-nines of API availability, there was a financial consequence to the business,” Larson recalls.)

His org took the idea one layer deeper and started setting targets for the number of production incidents they had. They assigned different levels of severity to incidents: low, medium and high. Across the eng org, success was tracked by how many high-severity incidents occurred, signaling to higher-ups that their team was focused on reliability. “This sparked an internal debate on if having targets around this was even helpful because people started to hide incidents,” Larson says. “There were debates on whether it would be more useful to have a target around customer impact of incidents. We really started to go all the way down.”

He remembers that his team and other eng leaders were frustrated by this, but to Larson, that was okay. “Again, it came back to this idea that measurements aren’t perfect. **The goal was to improve the mental model of how our leaders think about these areas.** Was tracking the number of incidents the perfect metric to start out with? No. But was it useful? Absolutely. It was a great platform to refine the company’s mental model on reliability,” he says. 

When you think about how to show off measurements to your CEO or your board, I would encourage engineers to worry less about things that offend their personal mental model, and think more about things that would inform the mental models of their board, their CEO, etc. 

If you are looking for more in-depth technical metrics that will help you gauge success, Larson recommends checking out [__DORA__](https://dora.dev/?ref=review.firstround.com), the more recent [__SPACE__](https://queue.acm.org/detail.cfm?ref=review.firstround.com) framework or the business software book [*__Accelerate__*](https://www.amazon.com/Accelerate-Software-Performing-Technology-Organizations/dp/1942788339?ref=review.firstround.com). But there is a caveat.

“The metrics in these frameworks are great for understanding where problems are, so you know where to invest so you can improve. But they're not going to increase engineering velocity from 100 to 120. They're simply going to say, ‘Deployments going pretty slowly right now, here’s where we can make an investment to improve deployment,’” Larson says.

“An easier way to think about what to measure is just by looking at when you drop below a target. That usually means that you want to invest a little bit more in improving those areas as well.”

People want metrics to show reality. They want them to show the truth. But metrics are only partly about showing the truth. The other half is about educating people, to inform their mental model about how the truth works.  

### **Pull your CEO into the details**  

Larson says that one of the growing trends he sees inside the engineering world that is challenging its leaders is an executive interest in volume.

“I remember one request from a CEO who wanted to understand the volume of the lines of code being written by the different engineers,” Larson says. “One challenge with that is there’s no direct correlation between the volume of code and the impact on the product. How do you track the value of people who are coaching others or improving the quality of others’ PRs against the folks who are actually contributing a significant amount of code? Sometimes more code is in fact worse,” he says.

“This is tricky because it's super nuanced. Within each pull request, there are the lines of code, sure, but some of them are bad,” Larson says. “Some of the lines of code are external libraries being added. Some of these are mostly tests, which are very valuable but might be very robust.”

When Larson is faced with executives or people pushing for specific things, he always takes it back to building their mental model. “I tell them that I’ll get them this data, but we have to talk through it,” he says. “Let's drill into it and understand the cases where this is actually a bad proxy. I think where I’ve gone wrong in the past, and where engineering leaders get into trouble, is by pushing back. They focus on saying ‘This is a terrible way to measure,’ instead of saying, ‘Let’s start here and drill in until we can understand the limitations of measuring this way.”

Trying to force people out of the details is never a good way to build alignment. You want to pull them into the details, and educate them there. 

## **UNEXPECTED ANTI-PATTERN #3: SERVING AS THE UMBRELLA FOR YOUR TEAM**

“There's this graphic that circulated a long time ago that showed managers acting as ‘umbrellas,’ protecting their team from interruptions and other managers who kind of direct problems at their team,” Larson says. “I used to be a big believer in the umbrella concept; I wanted to protect my team from the reality and problems around them so they could focus.”

The more senior teams I’ve worked with, the more I’ve come to believe that protecting your team from reality just makes things worse for them in the long term. 

Now, Larson tries to throw his team into the gory details much more quickly. “In the past, I used to think I was energizing my team by sparing them the details. But now it feels like lying to them,” he says. On a tactical level, Larson adjusted this habit by buffering less information. “That means even if it’s disappointing for folks, I’d rather them process news bit by bit, rather than deal with a huge ocean of mess all in one moment.”

One other tactic to try here is to simply give both managers and engineers a seat at the table when big conversations are being had, rather than relying on yourself to represent so many different viewpoints. “I’m a big believer in bringing folks into the room so that they can represent themselves rather than having small decision groups. I like working out problems in larger groups where you can hold people accountable for showing up in thoughtful and effective ways,” Larson says.

While we’re on the topic of bringing in more people, Larson also found that strategic decision-making is often in need of a fresh perspective. Whether you’re new to a company or have been scaling the same team for years, he examines the two most common approaches:

- **The Bottoms-Up Strategy.** This is the hands-off approach to management, where executives essentially just let teams execute on their own. The reigning theory here is that if something major occurs, like switching to a new cloud vendor or a team starting to use a different programming language, it will naturally escalate up to the CTO, who can pass judgment on it. “There's a good amount of literature about how this approach empowers teams to move quickly and have control over their tools,” Larson says. “The downside is you have no ability to make concentrated technology investments and you usually find out information a little bit too late. But in a growth moment where you have a ton of budget and you want to optimize for 1 in 100 wins, bottoms-up investments can be great.”
- **Top-down strategy.** The other common model is where a few senior folks (typically either a CTO or a handful of people who make up an architecture group) make most of the decisions for the whole org. But Larson says these aren’t always the best for every decision. “Chief architects and CTOs are pretty inefficient in terms of actually getting enough context in their heads to make a good decision on any given point,” he says. “Almost every architecture group turns into a committee where they have to balance their different perspectives, making them slow or inelegant.**It's rarely true that a committee gets the best decision, though the upside is it does at least bring all the context into the room.”**  

### **Use “Navigators” to Speed Up Decision-Making** 

Unsatisfied with the outcomes from both of these approaches, Larson decided to try something a little different for his latest role. “At Carta, we have a handful of different business units, so to [__speed up our decision-making__](https://review.firstround.com/how-to-make-decisions-faster/#to-evaluate-the-strength-of-an-idea-and-see-if-it%E2%80%99ll-have-staying-power-use-the-prfaq-approach-from-amazon-as-you-identify-key-assumptions-and-risks) we’ve been relying on people we call ‘navigators.’ Essentially, we appoint one person per business unit to act as a mini-CTO. They get to be the final decision maker for their area’s technology.” 

For example, think of the fund administration area of Carta’s business. “On that team, we have one navigator and 60 engineers working together. In many other areas at Carta, we’ve started rolling out Kafka as a messaging system, but the navigator in fund administration called out that they didn’t think it was the right tool for them to use. So they didn’t. We’ve seen a lot of success by empowering the folks with the most context on the ground to make the tech-stack decisions that make the most sense for them.”

Beyond this role being a good blend of different ways to execute, navigators call back to Larson’s earlier point on building a culture that rewards good judgment and leaders to spot changes and reverse course on the rules. If you are curious to try something similar for your org, Larson shares three lessons he’s learned so far: 

- **Don’t skip your documentation:**   “We have a written strategy there to guide navigators when making decisions,” Larson says. “They can make exceptions if they want to, and then they're accountable to me in terms of the exceptions they make. But it all gets written down.”
- **Do a post-mortem:** “I always like to follow up with navigators after a decision is made. This is mostly because I’m curious, but it also helps me to see around corners I might have missed.”
- **Be highly intentional in who you put conviction in.** While a pure management view dictates that companies should be resilient to departures and that[__people should not be load-bearing__](https://lethain.com/load-bearing-career-minded-act-two-rationales/?ref=review.firstround.com) , Larson ultimately feels that good judgment is difficult to replicate. So when choosing a navigator, don’t ignore your gut on who you trust. “You want to be extremely explicit in who is approved to exercise their judgment,” Larson says. “The point of a navigator is to have all questions routed up to one person, that’s not you as the executive. So spending time digging into people’s decision-making process is worthwhile.”

Organizations, even large ones, are just the culmination of a few individuals’ judgments. No amount of budget can allow you to escape that. 

Zooming out, as an engineering team starts to scale alongside a company, leaders shouldn’t lose sight of what has gotten so many well-meaning execs into messes before: Following the rules too closely. “Your ultimate goal is to create this high-quality mechanism around people being curious and looking for the exceptions,” Larson says. But that also doesn’t mean that leaders have to figure out the answers for everything alone.

Larson has been holding a bi-weekly [__“learning circle”__](https://lethain.com/rough-notes-learning-circles/?ref=review.firstround.com) for the past three and a half years. It’s a group of six to ten CTOs, VPs of Engineering or other senior engineering executives at tech companies who come together to catch up, exchange tactics and process issues together. 

“We start each meeting out by going around the room and giving each person one minute to say what they are focused on this week and give a topic they’d like to talk about. After five minutes or so talking about topics, we choose one as a group and spend the next 20 minutes or so really drilling into it,” he says. Topics range from “I’m getting screwed over by this project,” to “I just hired someone really good that I’m excited about.”

For those who learn by doing, leaning into routine reflections like a learning circle or solo can force the introspection needed to scale rules with nuance. “I’ve become a better leader learning from the lessons of others who have made similar mistakes before me,” Larson says.

*This article is a lightly edited transcript of our interview with Larson on the In Depth podcast. Go deeper by listening to the episode* *here.*