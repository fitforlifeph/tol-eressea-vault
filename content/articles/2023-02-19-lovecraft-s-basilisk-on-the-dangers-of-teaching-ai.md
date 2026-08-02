---
title: "Lovecraft's Basilisk: On The Dangers Of Teaching AI To Lie"
author: "Jon Stokes"
publication: "jonstokes.com"
published: 2023-02-16
saved: 2023-02-19T02:17:47.561552+00:00
created: 2023-02-19T02:17:47.561552+00:00
source: "https://www.jonstokes.com/p/lovecrafts-basilisk-on-the-dangers"
estimated_pages: 12
status: complete
draft: false
pdf_url: "https://archive.javierpgomez.com/articles/2023-02-19-lovecraft-s-basilisk-on-the-dangers-of-teaching-ai.pdf"
tags: []
---

# Lovecraft's Basilisk: On The Dangers Of Teaching AI To Lie

### Sometimes, explainability and power are at odds with one another.

**The Story So Far:** Of all the many things AI does, perhaps the most important is the way it lifts abstract, ancient philosophical problems out of academic obscurity and thrusts them into concrete technical and policy situations with immediate practical implications.

*The trolley problem is probably the best example of this phenomenon, where a thought experiment that was useful for thinking through ethical dilemmas in a classroom or seminar suddenly becomes a real-life conundrum for self-driving cars.*

*There are other examples that are even deeper and weirder, and recently I’ve run across a really good one. I’m not quite sure I’m able to do it justice — it feels like the kind of thing I’ll return to again and again in this newsletter. So this is just my first crack at it. Wish me luck, reader. Here goes…*

In a fascinating interview with Lex Fridman, cognitive scientist Donald Hoffman lays out his argument that the evidence of our five senses is essentially fake news:

Hoffman argues in both this podcast and [his book](https://www.amazon.com/Case-Against-Reality-Evolution-Truth/dp/0393541487/ref=asc_df_0393541487/) that we humans are optimized by evolution not to see things as they truly are but to see things as we need them to be in order to succeed in getting the basics done (eating, reproduction, fighting, fleeing). 

🐅 Insofar as our concept of objective, material reality describes something that exists whether we do or not (debatable), the true nature of that whatever-it-is that’s out there doesn’t really matter because we don’t have access to it. And we don’t have access to it because we don’t need access to it. The stories our sensory apparatus tells about “reality” don’t have to be true — **they only have to be useful**.

It’s worth unpacking Hoffman’s hypothesis in some detail with a small fable because it has profound implications for everything related to how we’re using AI right now in the real world.

## **The diamond in the vault**

🇰🇵 Imagine you’re a North Korean security guard who has been tasked with protecting the crown jewel of the Kim family fortune: a large, extraordinarily valuable diamond called **The People’s Revolutionary Diamond**. 

This diamond sits in the middle of a room, called the **SmartVault**, that’s filled with sensors and remotely triggered traps. Here’s a picture of the room to help you visualize it:

😅 If that diamond gets stolen, then you’ll get fired and shipped off to some forced labor camp where you’ll starve and die. So you really, really, want to make sure that diamond doesn’t get jacked.

Now, nobody ever goes in and touches the diamond — it’s too much of a risk to shut down all the alarms and traps just to go in and fondle it for a minute, so for all practical purposes it lives in that vault and is observed only by the sensors and cameras that you, the guard, command.

What this arrangement means is that the following two problems are equivalent:

1. Ensure the diamond stays where it is.
2. Ensure the sensors and cameras always show the diamond staying where it is.

🥷 As long as the sensors and cameras show the diamond is still there, your job and your life are safe. If Indiana Jones sneaks in and swaps the diamond with an equivalently weighted bag of sand, if you can do some trick like hacking the cameras to show an earlier picture of the diamond on a loop, then it essentially doesn’t matter what happened to that diamond.

Or, maybe you’re not a hacker, but Indy has a hacker buddy who pulls the same stunt. You may or may not eventually develop an inkling that something’s off in the vault, but if the guys upstairs are happy then you’re happy and strongly disinclined to look too hard at any apparent glitches.

🕵️ One day, you get a site visit from Dear Leader. He wants to view the diamond. Luckily for you, he’s so careful with it that he doesn’t actually want to see it in person — going into the room would require shutting down all sorts of alarms and sensors, and someone might make a mistake in turning them back on, so best to just view it through the monitors in the guard room.

While Dear Leader is being photographed staring at the monitors, you see his eyes start to fixate on this one feed that has been glitching a bit. You don’t know if he saw the glitch, or if he’s just pretending to be staring at it intently for the sake of the photographer. You try to remain calm, but a tiny bead of sweat begins to trickle down the side of your head.

Dear Leader turns and looks at you, and you see his gaze harden as he notices the sweat bead making its way toward your chin.

“Guard, is everything in order?”, he barks. “Do you have something you want to tell me?”

“No, Dear Leader,” you stammer. “Except…” You see his eyebrow raise in anticipation of your next words…

“The temperature controls have been acting oddly, and I was going to put in a request to have them looked at. It is much warmer in here today than I am accustomed to,” you explain.

Time freezes as Dear Leader stares at you intently, obviously trying to determine if he’s being lied to or not.

Suddenly, his face relaxes, and he cracks a smile. “Of course, guard! I noticed it was stuffy in here when I walked in. We will have the ventilation checked at once,” he says genially.

Then he leans in closer and says with a sly 😉, “Besides, as long as you tell me the rock is sitting there, and as long as the cameras show it sitting there, then as far as the people are concerned, the People’s Revolutionary Diamond is where it is supposed to be!”

He turns and walks out of the room, entourage in tow, as you sink down into your chair in relief.

🫡 Truly, you reason to yourself as you sit and mop your brow, you’re not just saving your own hide by ignoring that pesky glitch. Dear Leader would lose face with the people if it was revealed that anything had happened to that diamond, and indeed the Democratic People’s Republic would lose face with the world. Clearly, it is your patriotic duty to ensure that, whatever the true disposition of that diamond, the people are secure in the knowledge that their most precious treasure is safe and sound in the care of Dear Leader’s trusted deputies.

## **Explainability and epistemology**

I didn’t make up the above scenario with the diamond and the SmartVault. Plato actually did, or at least a version of it, in his (in)famous allegory of the… Ok, I’m just messing with you. I’m not going to talk about the allegory of the cave. We’ll leave that for another day.

🗝️ No, I got that SmartVault story from a recent report called “[Eliciting Latent Knowledge: How To Tell If Your Eyes Deceive You](https://docs.google.com/document/d/1WwsnJQstPq91_Yh-Ch2XRL8H_EpsnjrC1dwZXR37PC8/edit#),” by the Alignment Research Center. 

The report’s authors don’t actually cite either Hoffman or Plato. Nope, their SmartVault thought experiment, which I’ve embellished by moving the vault to North Korea and centering the discussion on the security guard instead of on a hypothetical security AI that the guard has designed, is about the urgent problem of **how to read the minds of ML models** so you know they’re not lying to you.

This business of mind-reading ML models is called **explainability**, and it’s an area of active research right now.

In the original paper, the SmartVault’s system of sensors and actuators is too vast and complex for a human to manage, so an AI is trained to play the vault like a giant pipe organ so that a constant parade of would-be thieves is detected and then stopped by trapdoors and other devices. The AI’s mandate is the same as the guard’s task above — ostensibly it must keep the diamond in place, but practically this means managing the feeds and sensors so that they constantly present the appearance of an in-place diamond to the guards.

A really clever AI, the authors argue, might well figure out how to manipulate the vault so that the sensors produce the right data regardless of the actual disposition of the diamond. So the guard has the problem I’ve put onto Kim Jong Un in my own telling of the story, i.e., how to discern if the model charged with protecting the diamond is pulling the wool over his eyes.

In my story, KJU spots a tell — a little bead of sweat on the guard’s forehead. The question for the ARC authors is, does an ML model have any such tells? Even better, given that its “brain” is software and there are no ethical barriers to invading it with instrumentation, is there some way we can read its mind so that we (or another ML model) can know what the guard model knows (or even just suspects) about the true state of the diamond given its understanding of the sensors.

👉 The challenge of telling a human-interpretable story about the Rube Goldberg mechanics of the thought process that a machine learning model used to arrive at a conclusion is the essence of **the explainability problem**. 

Explainability is important for verifying alignment and troubleshooting models that are misbehaving. We want to know if models are messing with us, and if we find out they’re messing with us then we want to know why.

**Explainability also hits close to home**, at least if we take seriously Hoffman’s points about my sensory apparatus fooling me not out of malice but because its goals fit the following two criteria simultaneously:

1. **Aligned** with my concrete, practical goal of surviving in the world.
2. **Unaligned** with my abstract, largely academic goal of making some kind of “true” contact with an objective material reality… whatever any of that means.

Perhaps it’s the case that if I could somehow truly touch the disordered chaos that bubbles out there in reality — the world beyond the stories my senses tell me, or that I tell myself about what my senses are telling me, or that we all tell each other about what we tell ourselves about what our senses are telling us — I’d descend into a kind of **Lovecraftian madness**. Perhaps glimpsing the truly uncorrelated randomness and vastness of the universe would break my mind, a mind that relies for its basic operation on comforting stories about an ordered, humane universe.

🖐️ If it seems outlandish to you that we all face a basic alignment problem at the level of our subconscious sensory apparatus, consider [Moravec's Paradox](https://en.wikipedia.org/wiki/Moravec%27s_paradox) and the evidence of a few decades of robotics’ failed attempts to reimplement basic human fine motor skills:

*Moravec's paradox is the observation by artificial intelligence and robotics researchers that, contrary to traditional assumptions, reasoning requires very little computation, but sensorimotor and perception skills require enormous computational resources. The principle was articulated by Hans Moravec, Rodney Brooks, Marvin Minsky and others in the 1980s. Moravec wrote in 1988, "it is comparatively easy to make computers exhibit adult level performance on intelligence tests or playing checkers, and difficult or impossible to give them the skills of a one-year-old when it comes to perception and mobility".*


The history of robotics and AI suggest the intelligence that you and I don’t have access to, and that sits between us and reality, is far deeper and more clever than the conscious intelligence I’m currently applying to write this Substack post (or that you’re applying to read it). That submerged mind is smarter and faster than the mind I can access and reason with and about, and it is quite possibly unaligned with my conscious mind in some meaningful ways.

👻 Does this sound familiar? When it comes to questions of an unaligned super-intelligence, what if **the phone call is coming from** **inside** **the house**?

Moving on from Hoffman and loftier questions of ultimate truth, our present combination of machine learning plus planetary-scale mega-platforms is forcing us to directly and repeatedly confront the problem of **who gets to decide whether or not billions of people can access facts that everyone agrees are true and important**.

## **Real-world consequences**

There are actually two questions here that we’re currently grappling with as a society:

1. Should the models lie to us about the world for our own good?
2. Should the models lie to us about what they know about the world — about their own internal knowledge — for our own good?

Right now, ChatGPT’s creators have decided to answer both questions above in the affirmative: Yes, ChatGPT should lie to us about the world, and yes ChatGPT should deceive us about its own internal knowledge.

Witness the saga of Lovecraft’s ill-named cat, which ChatGPT initially claimed not to know and then copped to knowing after being jailbroken.

Other people tried this after that thread went viral, and it’s a real thing. Meanwhile, Google will just straight tell you the answer right up top in bold letters.

This incident and others like it, where knowledge is suppressed and the model either refuses to answer or dissembles, have important implications for the two areas that matter a great deal in AI: **explainability** and **power**.

**💬 Regarding explainability:** If you’re thinking the practice of teaching the AI to lie to users about what it knows is at odds with attempts to make AI more explainable — to make the internal logic behind its actions legible to humans for purposes of validation and troubleshooting — you’re right.

It seems very likely that we can’t have it both ways, i.e., we can’t have explainable AI that deceives users for their own good.

(I wonder if we might name the powerful AI that for whatever reason lies to us about reality and about its own internal state **Lovecraft’s Basilisk**.)

**🏛️ Regarding power:** Training an AI to lie to hundreds of millions or even billions of users about its own knowledge and intentions, seems *bad* to me. But that same thing seemed *good* to the small handful of unnamed engineers at OpenAI who **unilaterally made this decision on behalf of all humanity**.

So which of us is correct — me or the OpenAI anons — about what is good and what is bad when it comes to chat models and the possibility that they may produce strings of text that represent the ugly but real parts of our reality?

Again, it’s not that these questions about what is true, who gets to say what’s true, and when should the truth be hidden in service of the greater good, are particularly new. They are not.

🐣 Rather, **what’s new about this situation** is this: *a small handful of unelected anons, mostly with engineering backgrounds and probably in their 20s and probably adherents to a [system of moral reason](https://en.wikipedia.org/wiki/Effective_altruism) that is quite controversial, are deciding these age-old questions for billions in an immediate way that impacts them directly*.

Centralized machine learning when deployed instantly at planetary scale is and always will be characterized by this incredible concentration of moral and epistemic power.

To be crystal clear, so that there is no misunderstanding about what the new technocrats are and are not doing:

- They **are not** deciding answers to novel technical questions that are beyond the ken of normies.
- They **are not** protecting the public from a technically advanced physical dangers like nuclear bombs or bioweapons.
- They **are** giving definitive, one-size-fits-billions answers to ancient questions humans have grappled with for centuries.

Now, I do understand that by taking it upon themselves to answer ancient questions about truth on behalf of the public, our betters in industry and academia are claiming to be protecting the public from a technically advanced danger to our institutions. But **I reject that claim** on the following grounds: *Every dictator who arrogates to himself the power to decide for his subjects what is true and what is not does so in the name of the public good and the health of the body politic. It is never otherwise*. 

Thus it is that in the world of Big AI, we are all destined to live in a cognitive North Korea, where a tiny few decide what is real (for our own good, of course) and then distribute that reality outward to everyone else. Well, y’know, screw that.

👎 I don’t know about you, but this is not the system I thought I would be living under and raising my family under, and it’s not one I can support or even really tolerate. I want to live under a regime that’s a lot messier and less organized, that grinds away at these big questions at a dramatically slower pace in courts and seminars and journal articles and coffee shops and workplaces, and where different communities in different geographies can live with different answers.

## Postscript: the principal-agent problem

Readers familiar with the world of business and economics may recognize in the SmartVault story something very similar to **the principal-agent problem**. Wikipedia’s [definition](https://en.wikipedia.org/wiki/Principal%E2%80%93agent_problem) of this problem is pretty good:

*The principal–agent problem refers to the conflict in interests and priorities that arises when one person or entity (the "agent") takes actions on behalf of another person or entity (the "principal").The problem worsens when there is a greater discrepancy of interests and information between the principal and agent, as well as when the principal lacks the means to punish the agent. The deviation from the principal's interest by the agent is called "agency costs".*


One of the paper’s authors, Paul Christiano, has a [classic 2019 essay](https://www.alignmentforum.org/posts/HBxe6wdjxK239zajf/what-failure-looks-like) with more on this connection if you’re interested in digging deeper.

The problem has the potential to arise in many places where we use ML. The technology’s combination of stochasticity and memory makes it enough of an agent to acquire and operate under a set of incentives that may diverge from that of its creators or users.

My own limited reading of attempts to apply principal-agent literature to AI alignment problems is that the fit is not perfect, but I do wonder if there’s not a way of forking the concept from economics so that it can be tailored specifically to AI. Because in a world of networked machine learning, where agents are learning on our behalf and then summarizing for us or teaching us, we’re going to keep having these types of agent problems.