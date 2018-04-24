---
layout: post
title: FOI Team GitHub Gardening
---

# {{ page.title }}

Extracted from an internal blog post on how I was thinking about prioritising work at the start of 2018.

<hr>

<p>This year I was in work between Christmas and New Year, which is a great couple of days to do some tidying up and prep for the year ahead.</p>

<p>I <a href="https://www.garethrees.co.uk/2018/04/23/moving-the-goalposts-closer-alaveteli-roadmapping/">posted about our roadmap process</a> earlier in the year, and while it didn&rsquo;t work out entirely as planned, the main ideas stuck.</p>

<p>The gist is that we set a higher-level goal each sprint and make that the focus.</p>

<p>Here&rsquo;s what Q4 2017 looked like:</p>

<p><img src="https://i.imgur.com/hmMcAbo.png" alt="Q4 2017 FOI Team Roadmap"></p>

<p>This has been working really well throughout the year by helping us keep a really clear vision of the work to prioritise during the sprints.</p>

<p>Now, the trickier bit is deciding exactly what work to do – and indeed what not to do – in that window.</p>

<h2 id="we&#039;ve-got-issues">We&rsquo;ve Got Issues</h2>

<p>A lot of issues, actually. 800+ in <a href="https://github.com/mysociety/alaveteli/issues">mysociety/alaveteli</a>, ~200 in <a href="https://github.com/mysociety/alaveteli-professional/issues">mysociety/alaveteli-professional</a>, and plenty more in the theme repos for individual installs.</p>

<p>This makes it <em>really</em> difficult to differentiate between &ldquo;we really should do this&rdquo; and &ldquo;yeah, that would be nice&rdquo;.</p>

<p>I had been thinking I want to comb these issues and do <em>something</em> with them to make them go away. Maybe close them; maybe migrate them to some other repository, but I&rsquo;d have to get through 2.5 a minute if I wanted to review them all in a single day. Lots of them are also valid issues or asks, so it doesn&rsquo;t feel right to close them. Instead, I&rsquo;ve decided that its a concrete reminder that there are <em>always</em> more things that could be done than you can actually do, and that what&rsquo;s more important is having systems in place to keep pushing forward.</p>

<h2 id="no-priorities?!">No Priorities?!</h2>

<p>I really don&rsquo;t want to assign priorities to issues because everything always seems to end up as &ldquo;high&rdquo;. Without constant attention, the &ldquo;high&rdquo; label sticks to the issue, even if our priorities change. As a team we&rsquo;ve got a fairly good mental picture of what needs improvement and what users are asking about, so the main concern is making sure we&rsquo;re juggling lots of high value work.</p>

<h2 id="feature-areas-&amp;-value">Feature Areas &amp; Value</h2>

<p>Instead I&rsquo;ve started creating some labels around <a href="https://medium.com/@rjs/managing-product-development-by-integrating-around-concerns-77640bcde28d">feature areas</a>. What I hope is that we&rsquo;ll get a good picture of areas of the product that have lots of discussion. This doesn&rsquo;t necessarily imply priority, just that there are lots of known options to explore.</p>

<p><a href="https://github.com/mysociety/alaveteli-professional/labels">Alaveteli Pro</a> is quite a good example of this right now.</p>

<p><img src="https://i.imgur.com/gk8n6ZV.png" alt="Alaveteli Pro Feature Areas"></p>

<p>The best combination of work to pick is where the result is of high value to our users and there are <a href="https://m.signalvnoise.com/running-in-circles-aae73d79ce19">few unknowns</a> with how we plan to solve the problem.</p>

<p>Our next main focus is improving the alpha version of batch. We <em>know</em> this is a high value area of the product because users have been repeatedly asking for it.</p>

<p>In the case of creating and managing batch requests we&rsquo;ve already got 13 fairly concrete options for improvement, so both can easily be scheduled for a sprint.</p>

<p>Batch analysis on the other hand is high value, but we don&rsquo;t have many open issues here. This implies one of two things:</p>

<ul>
<li>We&rsquo;ve already done a lot of the work, so the open issues might be an incremental gain.</li>
<li>We haven&rsquo;t thought much about this at all, and need to think about this at a higher level before we come to sprint planning and try to dive in to code.</li>
</ul>

<p>In this case, its the latter. We&rsquo;ve scheduled this for later in our Q1 2018 roadmap to give us some time to get some feedback from users and figure out what <a href="https://demandthinking.com/episodes/2017/8/29/episode-2-turning-big-unknowns-into-focused-projects">job</a> the feature is performing.</p>

<h2 id="milestones">Milestones</h2>

<p>I had been using <a href="https://github.com/mysociety/alaveteli-professional/milestones">GitHub Milestones</a> in a similar way top the feature labels above, but I think a better fit is for milestones to be mapped to the main sprint goal.</p>

<p>The milestone view is nice in that you can move issues up and down to create a prioritised list, so it makes keeping a prioritised backlog achievable now that we&rsquo;re dealing with a manageable subset of the total issues.</p>

<p>We also get an approximation of progress during the sprint through the milestone progress meters.</p>

<p><img src="https://i.imgur.com/9LDpKyz.png" alt="Alaveteli Pro Milestones"></p>

<p>There&rsquo;s definitely some overlap with <a href="https://waffle.io/mysociety/alaveteli">Waffle</a> here, so we&rsquo;ll see how that goes. I <em>think</em> that it&rsquo;ll work out like this:</p>

<ul>
<li>The milestones are more a planning tool for figuring out what&rsquo;s going to go in to the sprint for that focus area.</li>
<li>Once we start the sprint that focuses on the feature area, we push the issues through Waffle as its a better view of &ldquo;what&rsquo;s happening right now&rdquo;. There are always a some other bits and bobs that go in to a sprint outside of the main focus which would clutter the milestone views.</li>
</ul>

<h2 id="summary">Summary</h2>

<p>So here&rsquo;s an example of how we&rsquo;ll take a bit of an unknown feature (lets say, &ldquo;Batch Analysis&rdquo; – the things a Pro does once they&rsquo;ve received all the responses to their batch FOI request) to a sprint&rsquo;s worth of work.</p>

<ul>
<li><strong>Quarterly Planning</strong>

<ul>
<li>Schedule a sprint to work on Batch Analysis</li>
<li>Create a corresponding milestone</li>
</ul></li>
<li><strong>During preceding sprints</strong>

<ul>
<li>Work with support teams (design, comms, sales) to get a better understanding of the problem</li>
<li>Add issues to the milestone that would solve the goal</li>
<li>Keep shuffling the prioritisation of issues in the milestone view</li>
</ul></li>
<li><strong>Just before the &ldquo;Batch Analysis&rdquo; sprint</strong>

<ul>
<li>Label all the tickets in the milestone with &ldquo;2 - contender&rdquo; so that they appear in our plucking list in Waffle for sprint planning</li>
</ul></li>
<li><strong>&ldquo;Batch Analysis&rdquo; Sprint Planning</strong>

<ul>
<li>Go through our usual sprint planning process of assigning remaining work in progress</li>
<li>Load up the new availability with highest priority items from the contender list now containing Batch Analysis issues</li>
</ul></li>
<li><strong>&ldquo;Batch Analysis&rdquo; Sprint Retrospective</strong>

<ul>
<li>See how much work got done</li>
<li>Close the milestone – if issues didn&rsquo;t get completed this sprint, they should have to earn the right to get included in a future sprint. This might not always work if there are dependencies, but in general most of what we do isn&rsquo;t <em>urgent</em>.</li>
</ul></li>
</ul>

<h2 id="process-schmocess">Process Schmocess</h2>

<p>When you write this kind of thing down, it always comes across as being really rigid. In reality this is just a bit of a brain dump of what I&rsquo;m aiming at, and very much a set of guidelines rather than concrete rules.</p>

<p>I think the main takeaways from our 2017 roadmapping improvements were:</p>

<ul>
<li>Roadmaps should be about scheduling blocks of effort, rather than sequential completion of a checklist.</li>
<li>Being able to identify high-value, low-uncertainty work is more important than maintaining strict prioritisation.</li>
</ul>

<p>This year I think the main thing to improve is reducing uncertainty in the sprint goals before we come to work on them. I don&rsquo;t mean big design up front – just having some space to think about the things coming up so that when we get to them we&rsquo;re not finding ourselves needing to spend most of the sprint exploring before we can actually ship some work.</p>

<p>Happy New Year!</p>
