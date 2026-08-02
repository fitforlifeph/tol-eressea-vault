---
title: "How to design a house to last for 1000 years (part III)"
author: "Brian Potter"
publication: "Construction Physics"
published: 2022-01-05
saved: 2022-12-27T06:20:52.221877+00:00
created: 2022-12-27T06:20:52.221877+00:00
source: "https://constructionphysics.substack.com/p/how-to-design-a-house-to-last-for"
estimated_pages: 14
status: complete
draft: false
tags: []
---

# How to design a house to last for 1000 years (part III)

At last, we’re finally ready to put together the design for our house.

A fully specified design, with every detail and system described, is well beyond the scope of this newsletter (not to mention the scope of my knowledge). But we can give a high-level schematic design, laying out the basic building systems and how they’ll work together to satisfy our exhaustive design criteria.

### Foundation

The foundation supports the weight of the house, transferring its load into the ground below. It won’t get replaced unless something has gone catastrophically wrong, so we’ll need it to last the entire 1000 year lifespan of the house.

Typical single family home foundations consist of reinforced concrete, but reinforced concrete is a poor choice for a long lifespan building due to its susceptibility to corrosion. Unreinforced concrete is a much better choice. Unreinforced concrete was used for the foundations of the Roman Pantheon and Colosseum, and is still used today for [temple foundations](http://ecosmartconcrete.com/docs/trmehtalangley00.pdf) or other structures with extremely long design lives. We’ll want to use a specially designed, slow-curing mix to prevent the accumulation of thermal stresses - unlike conventional concrete which reaches its design strength in 28 days, ours will need at least 90.

Houses are light enough that their foundations can almost always bear directly on the soil. But this leaves the house susceptible to soil settlement and erosion - to prevent this, we’ll set our foundations on piles extending down to bedrock. These will be unreinforced as well (though corrosion will be less of a problem so far below ground).

Even though the load bearing elements are only on the exterior perimeter, we’ll extend the foundation under the entire footprint of the house. This should help prevent the dampness that’s often an issue with crawl space foundations (though we’ll want to make sure that this gets detailed in such a way to prevent water from accidently accumulating).

### Structure

On top of the foundation sits the framing. Our framing must do several jobs:

- It must resist normal gravity loads, as well as potentially extremely heavy lateral loads (earthquakes, tornados) or other extreme events (a tree falling on it, etc.)
- It should be strong enough to not sag significantly over centuries of life
- It must be resistant to corrosion and noncombustible
- It must interfere as little as possible with future rearrangement of interior partitions, or of building additions
- It must accommodate changes to building services as technology advances
- It must be relatively simple to repair or modify
- It should be legible - it should be easy to understand what it is and how it works in the absence of drawings or other information
- It should last the lifetime of the structure

It’s not trivial to accommodate all these requirements. After consideration, I’ve opted for a steel moment frame using built-up stainless steel plate girders and columns.

With this system, we can make the load bearing capacity essentially as high as we want it to (high enough that we should see very little sag, even over the long term). For lateral resistance, we’ll use a bolted fuse system (something like a [Durafuse](https://www.durafuseframes.com/)) at the joints, which will make repairs easier in the event of an earthquake or similar event. Because stainless steel has extremely high corrosion resistance, it’s unlikely to corrode even in the event of a severe building envelope failure.

This system will allow us to keep the interior of the house completely free of load bearing elements like walls or columns, making it trivial to rearrange the interior layout at a future date. And because it has a relatively small number of exterior columns, it gives a great deal of flexibility for exterior renovations, making it easy to expand add an addition, enlarge windows, or move doors.

We’ll also use a crawl space design, with the first floor supported by structural framing instead of the ground - this will allow us to easily repair or replace services in the future, as well as giving us some small degree of flood protection. To add to the flexibility, we can fabricate our beams and columns with openings in them to allow the future passage of services.

The flexibility and durability of this system should make it easy to justify renovating it. Substantial renovations of old buildings tend to be more expensive than simply tearing the old building down and putting a new one up, but steel frames are easy enough to reuse that keeping them is often the cheapest option. You frequently find them being repurposed even in buildings with no preservation value, like warehouses and industrial facilities.

Stainless steel plate girders is an unusual system for any building (much less a house), but conceptually it’s no different than conventional steel construction, and it should be understandable by future builders. And it’s highly tolerant of modifications - new components can simply be welded or bolted to it as needed. The one complication is that attaching dissimilar metals can lead to galvanic corrosion, so they’ll need to weld stainless steel or attach items using a non-conductive spacer. But this seems like an acceptable risk.

The main drawback of this system is fire resistance. Stainless steel is noncombustible, but it’s *not* fireproof - at high temperatures steel quickly loses strength, and stainless steel is no different (though stainless does have better high temperature performance than mild steel). 

We have a few ways of dealing with this. Using exceptionally thick flanges and webs should add some fire resistance, and will get us sufficient margin of safety that the building can remain standing even if the steel loses a substantial fraction of its strength. On top of this, we’ll protect the steel with something with a similarly long lifespan (which rules out spray-on fireproofing or intumescent paints). The best option here is something simple - we’ll encase the steel where possible with a thick layer of brick masonry or lightweight concrete panels.

These should limit the potential for fire damage - but we’re still taking a risk. For the truly paranoid, we could substitute the stainless steel for something like [Inconel](https://en.wikipedia.org/wiki/Inconel#:~:text=Inconel%20is%20a%20registered%20trademark,subjected%20to%20pressure%20and%20heat.), a Nickel-based “superalloy” that maintains its strength at much higher temperatures (in addition to being even more corrosion resistant than stainless). But not only would this be phenomenally expensive, it would add extra complexity that would make future modifications harder - the Venn diagram of “builders” and “people who understand how to repair or modify Inconel” looks like an eight. So we’ll stick with stainless.

Another drawback is weight - ideally our sections would be light enough that they could be manipulated by hand, but our steel sections are likely to weigh in the neighborhood of hundreds of pounds per foot. Since the steel is designed to be as permanent and unobtrusive as possible, this also seems like a worthwhile tradeoff.

We’re also taking something of a risk using something as valuable as stainless steel - a common failure mode for buildings is for valuable material to be ripped out and repurposed. This can range from looters [ripping the copper piping](https://www.thesilverlining.com/safety-tips/copper-theft) out of a house to sell for scrap, to Londoners [reusing the stones from ruined Roman buildings](https://www.reddit.com/r/AskHistorians/comments/537b5j/why_arent_there_ruins_and_buildings_from_roman/), to countries at war [melting down building components to make munitions.](https://legionmagazine.com/en/2018/11/the-seizing-of-europes-bells/) I don’t see an obvious way of addressing this problem - the risks of corrosion we’re avoiding with stainless steel seems like it’s worth the tradeoff, and covering it with masonry or concrete seems like it would make it less likely on the margin. But this is another reason not to use something as durable as Inconel - the value of the material would likely exceed the value of the building, which is inherently risky for long-term survival.

We’ll use stainless steel for the primary structural frame only - the columns and main girders. The infill framing can be something simpler and easier to work with. We’ll space our primary framing at about 12 to 15 feet, small enough that any number of possible floor framing systems will work. The best option might be the simplest, basic timber joists. Light enough to move by hand, more than sufficient load capacity, easy to modify, fasten to, or drill through, and easy to tear out and replace should the building be extensively renovated.

### Style and other design choices

For the overall design, we’ll go with something vaguely [Georgian](https://en.wikipedia.org/wiki/Georgian_architecture)/Georgian Revival. This style of house has been popular for close to 300 years, and can easily make the transition between a house that’s purchased for its functionality to something that’s preserved because of it’s architectural and cultural importance - perfect for our purposes. It’s simple roof design is excellent for shedding water and avoiding leaks, and the design can easily accommodate potential changes of use - it can easily become an office, or be carved into a duplex, or multiple apartment units, depending on what’s needed.

We’ll want to make sure the house has high ceilings, but not SO high that maintenance becomes burdensome (changing light bulbs and cleaning windows on 20 foot walls is not fun). 10-12 feet should work, giving us an overall floor to floor height of 12 to 14 feet. For a footprint, we’ll want to be in the neighborhood of ~30x60 - this will give us around 3000-4500 square feet.

We’ll want to make sure we include working wood fireplaces in our basic design. Keeping the interior warm is a basic function of a house, and being able to rely on externally supplied services (such as gas, oil, coal, or electricity) for heating is a relatively modern development, which could easily revert. But even if the grid fails and oil supplies run out, you’ll still be able to chop your own firewood.

### Exterior Wall

For the exterior wall, we’ll go with simple brick masonry. Masonry has an exceptionally long lifespan (if properly maintained), is durable, non-combustible, exceptionally impact resistant, corrosion resistant, and beautiful. Despite being an ancient technology it remains popular today, suggesting the skills needed to repair or modify it will likely continue to be available to draw on.

Most modern brick masonry (in the US, at least) is built using what’s known as a “cavity wall” construction - the brick is a thin cladding veneer, behind which is a layer of waterproofing and the load-bearing structure. This style of construction is used because masonry is porous, and water is able to work its way through the thin layer of veneer and collect on the interior. The waterproof barrier (and drip tubes at the bottom of the wall) prevent this water from damaging the house.

We can do better by using a more traditional double- or triple-wythe brick wall, which is thick enough to prevent water from making its way through it. Though in traditional construction a wall like this would be load bearing, for our house it will be a cladding wall only supporting its own weight - all the load will be taken by the steel frame. Though ideally the wall will last the life of the house, decoupling it from the load bearing elements will make the inevitable repairs and modifications.

We’ll want to use a traditional [lime mortar](https://stonemasonsedinburgh.com/use-lime-mortar-versus-concrete-mortar/) instead of more modern cement mortars. And because of brick’s porosity, we’ll want to have a non-porous material at the bottom of the wall to prevent it wicking water up from the ground. A base course of granite should work for these purposes. We can also use granite for lintels, arches, cornices, and other detailing (we’ll want to be sure to avoid any steel lintels or supports). Limestone would also work, but granite is more resistant to acidic water and thus will be more durable long-term. We’ll want to be sure that we include proper drip edges, that our [quoins](https://en.wikipedia.org/wiki/Quoin) are flush, and that in general there are no places for water to collect on the exterior.

Not only is a wall like this durable, but it allows the incorporation of the sort of architectural detail that makes buildings worth preserving. Old masonry walls are often worth saving [even when the rest of the building isn’t.](https://www.google.com/search?q=facade+retention&tbm=isch&ved=2ahUKEwjapZHizZP1AhXHE6wKHXfqCbgQ2-cCegQIABAA&oq=facade+retention&gs_lcp=CgNpbWcQAzIHCCMQ7wMQJzIHCCMQ7wMQJzIFCAAQgAQyBQgAEIAEMgUIABCABDIFCAAQgAQyBQgAEIAEMgUIABCABDIFCAAQgAQyBQgAEIAEOgQIABBDOggIABCABBCxAzoLCAAQgAQQsQMQgwFQ7QhY4BhgyBpoAHAAeACAAU-IAcEIkgECMTeYAQCgAQGqAQtnd3Mtd2l6LWltZ8ABAQ&sclient=img&ei=4-LRYZoox6ewBffUp8AL&bih=1067&biw=2939&rlz=1C1CHBF_enUS890US890)

One tricky thing with this type of assembly is that while it has performed well historically, it doesn’t necessarily play nice with [more modern, energy efficient](https://www.nrel.gov/docs/fy12osti/54163.pdf) construction. A solid brick wall was traditionally designed to be exposed on the inside, exposing it to interior heat and allowing it to dry. Adding interior insulation makes the house much more comfortable, but also changes the thermal dynamics, potentially causing freeze/thaw damage in the brick, and allowing moisture to accumulate between the brick and the insulation. This is one of the many details that would need to be worked out for the complete design of the home.

For windows, we’ll use hardwood timber windows, which are more durable, maintainable, and repairable compared to modern options like vinyl or fiberglass. And we’ll want to make sure we install vents in the proper location (taking care to ensure they won’t be able to catch flying brands from an outdoor fire).

### Roof

For the roof, we should choose a system with the understanding that it will likely need to be replaced at some point, possibly with a completely different system. But the longer we can go without needing to do that, the better off we’ll be. For long lifespan, we have roughly two options: metal or slate.

For metal, the easiest option is something like a galvalume (NOT galvanized) standing seam roof. These can have incredibly long lifespans (100+ years), are lightweight, are easy to install, require little maintenance and are very common. The main drawback is that it can have a less appealing, somewhat commercial look - not ideal for a building we’re trying to inspire others to maintain for centuries.

Copper is another metal option. It also can last a long time (though not indefinitely), and can have a more attractive appearance. But we trade off increased upfront expense, and probably more difficulty in finding skilled workers that can repair it.

Our other option is slate. Slate roofs have extremely long lifespans and are extremely attractive. But, like copper, they’re more expensive upfront, and require more specialized skills to install (since they’re less common). A slate roof is also extremely heavy, putting more weight on our framing and increasing the risk of damage during an earthquake.

We’ll go with slate, as I think the combination of empirically long lifespan and ability to convince people “this is a building worth saving” is more valuable than the drawbacks. Different slates have different durabilities depending on the type of rock used, so we’ll go with [Buckingham Slate](https://en.wikipedia.org/wiki/Buckingham_Slate), which has a manufacturer’s warranty of 150 years (!) We’ll pair this with copper flashing and gutters/downspouts.

### Other building systems

It’s much less important to be picky about the other systems - anything on a faster pace layer will inevitably be replaced after a small fraction of the building's life, and the design of our framing system should allow them to be swapped out relatively easily. So I’ll just give a cursory overview of them.

For mechanical, electrical, and plumbing systems, we should simply use whatever best practices dictate at the time and in the immediate area. The same is true for partition walls - whatever is in common use is likely fine. It may be marginally preferable to use light gauge steel instead of wood stud walls, as it will add less to the combustion load and be less likely to be damaged by rot or corrosion. But it’s a fairly minor consideration.

The same goes for flooring - it will also likely be replaced multiple times over the house's life. We should choose something that’s nice, that’s easy to work with/modify, and that’s durable. Solid wood flooring and clay tile (for the living areas and kitchens/bathroom, respectively) should work here.

For future renovations, it’s useful to have as much information about the building as possible. Since drawings are likely to be lost over a period of 1000 years, we can help future builders by embossing design information such as design loads, material properties, foundation extents, etc. on a stainless steel plate welded to one of the girders:

### Location

When choosing a spot to build, we should pick somewhere that has a long history of being a desirable place to live, that has a mild climate, and has as few potential natural disasters as possible. If we’re truly optimizing for lifespan to the extent that we can pick anywhere, London seems like a good choice. It has a 2000+ year history of being inhabited, it seems likely to remain an urban area of importance, it has exceptionally old building stock (making it less likely our house will be torn down, and that people are used to living in and modifying very old buildings), and it has a robust system for dealing with old and historically valuable buildings (as well as [protecting the knowledge](https://heritagecrafts.org.uk/redlist/) for how to work with them). It has a relatively mild climate, and little natural disaster exposure (low potential for wildfires, earthquakes, hurricanes, or tornados). 

But there’s so much uncertainty around what the future holds that any major urban area can probably work - in the US, somewhere like New York or Boston would be a reasonable choice (though they have harsher climates than would be ideal).

Once we’ve picked an urban area, we should make sure to build on elevated ground (well outside of the [Thames floodplain](https://twitter.com/MapsFg/status/1352328724306341900/photo/1) if we’re sticking with London). The plot of land should be a local high-point that won’t accumulate water, close enough to the city that it’s a desirable place to live but not so close that it’s a candidate for being torn down and replaced with denser construction in the near-term (long-term, the hope is that our house will be culturally valuable enough that this is no longer on the table).

### Conclusion

The design of this house is about knitting together the two ways that buildings get kept around - because they’re economically viable, and because they have cultural and historic value. The hope for our house is that as the potential for the first wanes, the potential for the second keeps increasing. The outer shell is designed to be exceptionally durable while making it as easy as possible to make repairs and modifications. Virtually everything inside the outer shell can be torn up and repurposed as needed. This will hopefully allow it to adapt for many possible future uses while still keeping its architectural character, allowing it to steadily increase in cultural value until that’s reason enough to keep it around.

Would we be better off if the typical house were designed to last 1000 years? I think it’s hard to make that case - we haven’t considered cost in this exercise at all, but the cost of the design above would be substantial, probably in the neighborhood of $1000-2000 per square foot (8 to 16 times as much as conventional construction), and we’ve screened off many possible locations where empirically people are interested in living (such as the entire west coast of the US).

But this was specifically designed to optimize lifespan above all else. Switching out some of our choices for cheaper ones (conventional steel frame instead of stainless, normal spread footings instead of piles, Building Science’s 500-year wall instead of multi-wythe masonry, galvalume roof instead of slate) would still have the potential for multi-century lifespan at a much more reasonable cost (probably $200-300 per square foot, close to conventional commercial construction).

Surely this would be worth it, right? I think even this is hard to say. Extending the lifespan of the built environment is valuable (the replacement cost of all buildings in the world is something like $165 Trillion) [0], and being able to keep old buildings around and useful is in some ways accumulating cultural value that otherwise wouldn’t exist. But keeping old buildings around prevents new buildings from taking their place - London has lots of old buildings, but it also has exceptionally low worker density, which means it’s failing to capture many potential agglomeration benefits. And building houses with extremely long lifespans would likely mean that we’d end up with significant infrastructure and investment in places it’s not needed, since urban areas shift in importance over time.

Designing a building for an extremely long lifespan is in some sense a bet on a certain kind of future - one where tomorrow’s physical infrastructure needs aren’t all that different from todays. And because physical infrastructure is hard to change once it’s in place, it’s also an attempt to bring that kind of future into existence. But if you think agglomeration effects should push cities to get larger and denser, or if you think we’re likely to see some cities shrinking as the nature of the economy changes, or if you think building technology is likely to change significantly, an extremely durable, an extremely long-lived house is perhaps less desirable.

*These posts will always remain free, but if you find this work valuable, I encourage you to **[become a paid subscriber](https://constructionphysics.substack.com/publish/settings/https://www.construction-physics.com/subscribe?).** As a paid subscriber, you’ll help support this work and also gain access to a members-only slack channel.*

*Construction Physics is produced in partnership with the Institute for Progress, a Washington, DC-based think tank. You can learn more about their work by visiting their [website](https://email.mg1.substack.com/c/eJwlkN2OhCAMhZ9muDSAiHjBxd7Maxgs1SGjYKDsxrdfnEmaNulPTr8DjnBL-bJnKsTuNNN1oo34V3YkwsxqwTwHb_tBGMEN85aPEsaFhTKvGfFwYbfsrMsewFFI8V4WXPHBsJc1bhH9YLgRTsKwwqSU9hIconT9otxX01UfMAJa_MV8pYhsty-iszz6n4d8tjhz2jKW0oVYKFAlbE0WrOSyhZBCq0nyTnYapxWh9bQBLVbfvYu5YFTuofixia7UpZCDdwfpYNkuObgIZ7pR28Z203xGDWhu9agx0DVjdMuO3lKuyOjr1od83jBibi762ZFtXyht1KCb_vRFa2Yoo4exF4Y1bZ_aVbSQGkaucPt1vq4SoPwDXP-Gfw).*

*You can also contact me on [Twitter](https://email.mg1.substack.com/c/eJwlUEuOhCAQPU2zNID8XLCYzVyDIBQ2aQUDOB1vP6hJpQhF8X7ONlhyOfWea0NXM-3cQSf41hVag4KOCsVEr0dOFMEKeY0ldXJGsZpQADYbV432Y16jsy3mdC0TzDBX6K3HgP1EiPTS8ikoNnrlOOaSiRA4B_Jw2sNHSA40_EE5cwK06ndre32NPy_626t946VmcHnrNzOXaNOeb4FRU0x7EUoEmyge6CBgCuD6TCgnSPDDp6rTSWZfDG8LGeox12bd54JDRd9o7oHrG8tl6X7qrkw_tyPFdhpIdl7B61YOQO2J7LZvFkhQepTe2Ka7CiYU46LzT4-_nghTgsuRKNS5fe6_knY51Y7lrtD291mjq_-RvYff), [LinkedIn](https://email.mg1.substack.com/c/eJwlUMGuhCAM_JrltgZQEQ8c3uX9hoFSXbIuGMBn_PtX16QpybTMdAZsxSXl02ypVHa1qZ4bmohHWbFWzGwvmKfgTdsLLbhm3vBBwuBYKNOcET82rIZtu1sD2BpSvJYF73iv2cv4bm7BtqPkwEcHDkYp-Gzbdpx7kOhuTbv7gBHQ4B_mM0Vkq3nVupVH-_OQv1THcTRriG_0ITaQPgSFSM3lYONzS9epT2W5lqLnhLNgJJdUQgrVkXwjG4XjjECY0qDE7Jt30ScMnX10_LOIpuyuVAvvi59l86WGm5o2lsvod0ReJ3o_ewz1nDBat6I3Ne_I6h3kN5RpwYiZAvaTrYau6JTuekX64-2acuq06odWaEbaPtGvaCDFQlxwRbm9zhKg_AMGHI5O), or by email: [briancpotter@gmail.com](mailto:briancpotter@gmail.com)*

*[0] - Worldwide there was an estimated 225 billion square meters of building floor area in 2015 ([Lagaros 2018](https://www.researchgate.net/profile/Nikos-Lagaros/publication/324965158_The_environmental_and_economic_impact_of_structural_optimization/links/5af29cf3a6fdcc24364f3148/The-environmental-and-economic-impact-of-structural-optimization.pdf)), roughly 330 square feet per person. Assuming an average cost of construction at $750 USD per square meter, that represents $165 trillion worth of assets.*