---
layout: post
title: The Problem with Roadmaps
---

# {{ page.title }}

I’ve recently been reading some Christopher Alexander and I’ve found that so much of his theory of Organic Order applies to how software projects grow and get planned.

The “Master Plan” approach typically taken by community administrators is analogous to software roadmaps, and so are the problems that come with it.

Not all roadmaps will suffer from all of the problems at the same time, but they're all ones to watch out for if you're using roadmaps in your project.

<h2 id="knowledge">🔬 Knowledge</h2>

You'll know more tomorrow than you know today, but a roadmap is a fixed definition of a “good” plan based on today’s knowledge. Also, plans rarely survive contact with reality. A roadmap then, is not agile, so its suitability can be affected by change.

<h2 id="time">🕑 Time</h2>

As you develop the features along a roadmap, your idea of how the whole system should interact will inevitably change. This may require rethinking future roadmap items, or even replacing them altogether. The rigidity of roadmaps makes this less likely, as the people making these observations will have little [control](#control) over the direction and little desire to think about [making more work](#debt).

There’s also the possibility that the world changes around the roadmap. You may have started development on a Blackberry app, but should you continue with your roadmap as you watch the iPhone becoming ever more popular?

Over time a roadmap increasingly loses its relevance as knowledge improves and change happens, until finally people ignore it – or at least [lose faith](#morale) in it – because it no longer tells them anything useful.

<h2 id="debt">💸 Debt</h2>

A roadmap creates a continuous burden of debt that can never be repaid. The further ahead the roadmap looks, the greater the weight of the debt.

Debt makes a team inflexible. They’re hardly going to entertain responding to changes in the environment or the system if they’ve _already_ got a pile of commitments ahead of them.

A team that is focused on churning through a mountain of work will never have the headspace to invent a better way.

It also creates a [morale-suppressing](#morale) feeling of being on a continuous treadmill, turning skilled, creative workers in to burned out drones.

<aside class="minor-note">See <a href="/2018/06/30/book-notes-peopleware/">Peopleware</a> for notes on curating an inspiring and productive workplace.</aside>

<h2 id="morale">😔 Morale</h2>

Roadmaps create a frozen future where people feel they can only affect relatively trivial details. They then lose a sense of ownership and responsibility for the system and instead feel like a cog in a machine.

Enthusiasm is crushed by a perception of slow speed to get simple things done. The roadmap kills spontaneity because new work gets added to the very distant end. The [budgeting process](#budget) of roadmaps makes smaller tasks less likely to even get committed to in the first place.

<h2 id="budget">🍰 Budget</h2>

There is a tendency for only large projects to get allocated space on a roadmap (Alexander calls this “large lump” development). In large lump development the total budget spent on large projects is typically far greater than the total budget spent on small projects.

This is in part due to the possibility that new budget may not become available, so we must get all the large features built while budget is available; the small stuff can wait.

It also assumes that feature development will be perfectly executed every time. This is almost never true, so each feature will bring with it a new list of [bugs, improvements and enhancements](/2018/08/12/bug-improvement-enhancement/). 

New features are almost always shipped in a flawed state, so the budget available must include resource for modification, repair and maintenance. This is almost never scheduled on a roadmap, so new features never mature to be truly fit for purpose. Over time this creates “slums” in areas of the system as they receive limited attention. These slums eventually get replaced a new large lump development – based on more current knowledge – but suffer the same fate.

<h2 id="control">🛂 Control</h2>

Roadmaps are usually set by a Project Manager or leadership team; maybe there’s input from subordinates. This creates problems other than [a lack of morale](#morale).

There are always more possibilities for development than you can ever hope to do, so smaller projects always seem to sink to the bottom of the priority list over more “visible” large projects.

The detachment from the user also increases this tendency towards large projects. Roadmap controllers can picture the shape of large projects to a degree, even if they don’t have all the implementation details worked out. They can appreciate X not existing, but X will exist once built – a clear transformation. They’ll never really understand the impact of really small details that regular users bump in to day after day in the existing system though.

The single controlling entity also results in a limited diversity of opinion in the [budget](#budget) allocation process. All work should receive input from a cross-section of actual users of the feature.
