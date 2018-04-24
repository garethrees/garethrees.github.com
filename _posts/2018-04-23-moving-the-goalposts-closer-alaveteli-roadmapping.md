---
layout: post
title: "Moving the Goalposts Closer: Alaveteli Roadmapping"
---

# {{ page.title }}

Extracted from an internal blog post on how I was thinking about the roadmap for Alaveteli at the start of 2017.

<hr>

<p>In January 2017 we had some ideas about how to tweak our roadmap planning so that it helps us hit targets. What follows is what I wrote up after our Q1 Alaveteli team meetup. After that I've added some notes about how its working so far.</p>

<hr>

<p>Over the last year or two we’ve been really trying to make more intelligent choices about what we work on.</p>

<p>Two vital parts of this decision process are:</p>

<p>
<ul>
  <li>Defining the goal</li>
  <li>Measuring the result</li>
</ul>
</p>
 
<p>We’ve got a really high level goal of getting 7 impactful Alavetelis in 2017. The measurement of that is a familiar phrase:</p>

<blockquote>A deployment that receives either at least <strong>125,000 sessions</strong> in any rolling six month period in the target year <strong>or</strong> facilitates at least <strong>2,500 transactions</strong> in any rolling six month period in the target time period</blockquote>

<p>
There are countless features, bug fixes, UI tweaks, marketing campaigns, user tests, growth hacks, etc that we can choose to work on to try to achieve this goal. We face this decision every two weeks, when we try to select a new chunk of work to push us towards our goal.
</p>

<p>
We know it's almost certain that we won’t hit this goal in the space of a sprint, and just as unlikely that we’ll hit it in a quarter. The granularity of this goal isn’t aligned with the granularity of our short-to-medium term planning.
</p>

<p>To try to help with these shorter term decisions we’ve been using a roadmap loosely based on a version of <a href="https://insidegovuk.blog.gov.uk/2014/07/31/experiments-in-roadmapping-at-gov-uk/">GOV.UK’s roadmap experiment</a>.</p>

<figure>
<a href="http://i.garethrees.co.uk/alaveteli-roadmap-2017-current.jpg">
<img src="http://i.garethrees.co.uk/alaveteli-roadmap-2017-current.jpg" alt="Alaveteli Roadmap 2017 Current">
<figcaption>Alaveteli Roadmap 2017 Current</figcaption>
</a>
</figure>

<p>Our current bi-weekly sprint planning process involves plucking an assortment of tickets from the the contender list (loosely prioritised around work on the roadmap and new, urgent work). While getting lots done, it can feel like we’re not making traction in any specific direction towards our yearly goal.</p>

<p>I think there are several problems at play that’s causing this feeling.</p>

<p>
<ul>
<li><strong>Goals should have measurements.</strong> We don’t have specific measurements for many of our roadmap items. We can say they’re done, but we don’t know whether they were worth doing.</li>
<li><strong>Goals and measurements should be at a granularity appropriate to the planning period.</strong> Some of our roadmap items are quite high level; some might take a few days of work.

<ul>
<li>Its hard to know when to plan these in for. Do we attempt an item during a sprint, or make it a goal for the quarterly plans?</li>
<li>Its difficult to know if we’re making traction on the items that we don’t have specific measurements for.</li>
</ul></li>
<li><strong>Goals and measurements should be directly linked to the less granular ones above.</strong> When we’re planning a sprint, we should be aiming for the work to directly impact the quarterly goals. When planning the quarterly goals, they should be aimed at hitting the yearly goals.</li>
<li><strong>No more than a handful of goals per planning period.</strong> A narrower focus at all levels helps to push towards our goal for the period. This is most noticeable in sprints, where effectively every ticket is a goal. That’s probably around 30 goals for the team every two weeks.</li>
</ul>
</p>

<p>I think we can build an improved roadmap that has a direct line from what you’re doing on a given day to the main yearly goal of the project.</p>

<p>We have three main planning periods to account for, each of which need appropriate goals and measurements.</p>

<ul>
<li>Yearly (Funder targets)</li>
<li>Quarterly (Alaveteli team meetups)</li>
<li>Bi-weekly (Sprint planning)</li>
</ul>

<p>These goals should be more achievable in the given time period, and designed in a way that hitting them all throughout the year increases the likelihood of hitting the yearly goal.</p>

<h2>Yearly</h2>

<p>We’re pretty clear on our yearly goal and how to measure it. Easy!</p>

<figure>
<a href="http://i.garethrees.co.uk/alaveteli-roadmap-2017-yearly-goals.jpg">
<img src="http://i.garethrees.co.uk/alaveteli-roadmap-2017-yearly-goals.jpg" alt="Alaveteli Roadmap 2017 Yearly Goals">
<figcaption>Alaveteli Roadmap 2017 Yearly Goals</figcaption>
</a>
</figure>

<h2>Quarterly</h2>

<p>This is where we start to lose the direct line between granularities.</p>

<p>Our current roadmap headlines are:</p>

<ul>
<li>5 sites operating at 125,000 visits or 2,500 transactions over 6 months</li>
<li>Clear, modern codebase</li>
<li>Fully internationalised, easy to customise</li>
<li>Stable, bug-free, maintainable</li>
<li>WDTK support</li>
<li>Security</li>
<li>Features</li>
<li>Improved UI</li>
</ul>

<p>We’d all agree that these are Good Things, but I don’t think we can directly relate any measurements of the above to the main team goal.</p>

<p>Here’s what we <em>can</em> measure, that have a direct impact on the outcome of the yearly goal.</p>

<ul>
<li><strong>Acquisition</strong>: Get new users.</li>
<li><strong>Engagement</strong>: Keep users using.</li>
<li><strong>Retention</strong>: Stop users leaving.</li>
</ul>

<figure>
<a href="http://i.garethrees.co.uk/alaveteli-roadmap-2017-quarterly-goals.jpg">
<img src="http://i.garethrees.co.uk/alaveteli-roadmap-2017-quarterly-goals.jpg" alt="Alaveteli Roadmap 2017 Quarterly Goals">
<figcaption>Alaveteli Roadmap 2017 Quarterly Goals</figcaption>
</a>
</figure>

<p>New users directly increase the transaction and session counts toward our main goal.</p>

<p>Repeated use directly increase the transaction and session counts toward of our main goal.</p>

<p>Users leaving directly <em>decreases</em> the transaction and session counts toward our main goal.</p>

<p>Each quarter we can review these three metrics and set an achievable improvement target (e.g. +10% Acquisition). An improvement means that we can be confident that we’re on a faster course to hitting our main target, since each goal at this level directly impacts the 7 successful sites goal.</p>

<h2>Bi-weekly</h2>

<p>As mentioned, I don’t feel we have a solid direction when it comes to sprint planning; partly due to the vague quarterly goals, but also because we don’t have a main goal at each sprint. The problem here is that we’re <em>too</em> granular. Each ticket we pick is effectively a single goal for the sprint. We all end up with 5–15 tickets, so that’s around 30 goals for the team in a two week period!</p>

<p>With so many goals, its too difficult to measure the impact of any one item against our medium term goals.</p>

<p>Each sprint we should focus our efforts around a single goal intended to improve one of the quarterly areas of focus.</p>

<p>For example, if we were focusing on “Engagement”, a sprint goal might be “Increase use of the request classification game”.</p>

<figure>
<a href="http://i.garethrees.co.uk/alaveteli-roadmap-2017-sprint-goals.jpg">
<img src="http://i.garethrees.co.uk/alaveteli-roadmap-2017-sprint-goals.jpg" alt="Alaveteli Roadmap 2017 Sprint Goals">
<figcaption>Alaveteli Roadmap 2017 Sprint Goals</figcaption>
</a>
</figure>

<p>At the start of the sprint we’d do some quick investigation in to how best to measure the usage and how much we think we can increase it. Then the whole team can work towards making that happen. How might that look?</p>

<ul>
<li><strong>Designers:</strong> Improve the interface; add new call to action links</li>
<li><strong>Marketing/Comms:</strong> Create social media adverts and Adwords</li>
<li><strong>Developers:</strong> Fix known bugs with the game; integrate design work; create marketing mail to send to users; add analytics conversion tracking.</li>
</ul>

<p>Maybe this will take up the majority of the sprint, or maybe it gets done in a handful of days. If the latter is true, then the team can either iterate on the same theme if there are obvious improvements to be made, or turn our attention to more general work like partner requests, general bug fixes, or other lower priority issues. The main thing is that we aim at one goal, and ask “What stopped us achieving the sprint goal?” if we didn’t hit it.</p>

<h2>Health</h2>

<p>I think its also important to consider the “health” of the project.</p>

<p>We’re spending the first 3 months of the year paying off some technical debt (Rails upgrade, spam prevention measures, scaling WDTK, etc) and I’d shoehorned that in to retention with the thought that bugs and security issues can mean users get frustrated and leave. While I think this is somewhat true, I think its a different problem.</p>

<p>Here’s a better analogy; you can still come to work and get things done while you’re ill, but you’re going to be inefficient (either through being slower, or by making mistakes). If you keep on pushing through this, after enough time you’re going to make yourself seriously ill and burn out; or worse.</p>

<p>I think the same is true of a project. We can keep running with a really low code quality score, but its making development slow. We can ignore the community update emails, but one day our community will have vanished.</p>

<p>While health may not directly increase or decrease our three areas of focus, I feel pretty confident that poor project health will make everything we do much harder than it needs to be, so we need to put intentional effort in to keeping the project healthy</p>

<p>While the main goals above are quite “business” focused, I see health more directly related to job roles:</p>

<ul>
<li><strong>Programmers:</strong> Code quality; error rate; test coverage; Apdex score</li>
<li><strong>Partner Manager:</strong> Community updates; time to resolve partner queries; partner Adwords usage; conferences</li>
<li><strong>Designers:</strong> Accessibility scores; optimised images; responsive versions of pages</li>
</ul>

<p>I haven’t given all these metrics much thought, but I think we should aim to track them on a traffic light scale.</p>

<ul>
<li><strong>Green:</strong> All good. 80%+.</li>
<li><strong>Yellow:</strong> Causing a few irritations and hiccups, but still sustainable for a while. 40–80%.</li>
<li><strong>Red:</strong> Some serious problems here. Can keep going, but this is definitely going to be causing some problems somewhere. &lt; 40%.</li>
</ul>

<figure>
<a href="http://i.garethrees.co.uk/alaveteli-roadmap-2017-overview-painted.jpg">
<img src="http://i.garethrees.co.uk/alaveteli-roadmap-2017-overview-painted.jpg" alt="Alaveteli Roadmap 2017 Overview">
<figcaption>Alaveteli Roadmap 2017 Overview</figcaption>
</a>
</figure>

<h2>Pulling it all together</h2>

<p>With appropriate scale goals for the size of planning period, deciding priorities is much easier:</p>

<ul>
<li><strong>Yearly:</strong> Decide how many platinum sites we’re aiming for</li>
<li><strong>Quarterly:</strong> Decide which areas of focus need work and plan six sprint goals (~2 sprints a month for 3 months)</li>
<li><strong>Bi-weekly:</strong> Decide the main things that need doing to hit the sprint goal; pick some fallback tickets if there ends up being slack in the sprint</li>
</ul>

<figure>
<a href="http://i.garethrees.co.uk/alaveteli-roadmap-2017-goals.jpg">
<img src="http://i.garethrees.co.uk/alaveteli-roadmap-2017-goals.jpg" alt="Alaveteli Roadmap 2017 Goals">
<figcaption>Alaveteli Roadmap 2017 Goals</figcaption>
</a>
</figure>

<p>We also need to find ways to keep the project healthy while continuing to hit our goals. Here are some suggestions:</p>

<ul>
<li>Spend Fridays working on improving health, until everything is “green”.</li>
<li>Every quarter, plan 5 goal-related sprints and one health-based sprint.</li>
<li>Every sprint, have one person dedicated to improving a health issue, while the rest of the team works on the sprint goal.</li>
</ul>

<hr>

<h2>Q2 Update</h2>

<p>We decided to spend at least Q1 paying off some technical debt. The majority of this was Rails upgrade and spam prevention, which spilled over in to Q2. We're about on track to get to 4.2 by the end of Q2, but there's still Rails 5.0 and 5.1 to get to. It's really important to keep on top of framework upgrades, because they get increasingly difficult as you write more code against older versions.</p>

<p>While technical debt payoff doesn't really fit in to this approach (very much developer focussed planning, and unlikely to move metrics), something I found early on was that having the sprint goal really helped with prioritisation in our sprint planning sessions. It's much easier to decide whether a less urgent ticket can be squeezed in based on how confident we are about the sprint goal.</p>

<p>One concern about this format is that we might miss important tickets that aren't obviously part of a theme. So far we've been able to keep fairly well to the quarterly roadmap while also tackling small tickets during the sprints, but we'll probably end up making 2 in 6 sprints "Junk Drawer" sprints, where we just mop up lots of these types of tickets in one batch.</p>

<p>At the moment we don't have very good visibility of the individual transactions that make up the transaction stats in ProjectDB. We're hoping to be able to graph daily counts of these by the end of Q2 so that come Q3, we can actually have a stab at working to boost the rate of one of the transactions. Once we get in to this I'm sure we'll encounter difficulties and tweak our processes, so I wanted to share where we are so far before it gets too out of date!</p>
