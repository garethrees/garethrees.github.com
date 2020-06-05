---
layout: post
title: "Managing technical debt is like managing a garden"
---


# {{ page.title }}

Manufacturing analogies are often used for software development, and while they make sense for some parts of the process, a lot of the times they don't stack up.

Manufacturing tends to be focused on churning out identical widgets. Some widgets are complex –  cars for example – and have been designed for maintenance and minor modification, but on the whole widgets are pretty static objects with no life of their own.

The software systems we tend to write are much closer to living ecosystems. Our software systems are built for change and run in contexts where external forces impact the system, even if it goes untouched by us. A car kept in a stable environment with no use will be almost as factory fresh after 50 years as it was when it rolled off the line. This isn't the case with a garden. Nature's forces will take control, and while you may be left with something beautiful, the formal garden you left will be long-gone.

Here are a couple of analogies to gardening that might help visualise some programming concepts that can be tricky to understand unless you've faced them yourself.

![Photo by Ignacio Correia on Unsplash](/images/posts/ignacio-correia-1_yycyoMT6g-unsplash.jpg)

**Pruning:** Pruning keeps the visible edges of a garden tidy. Pruning herbs promotes new growth and keeps the stems soft and edible. You often notice when pruning doesn't happen as you can see the effects easily – borders overflowing on to a path, or an overgrown bush blocking out a smaller plant. A bit of character is fine – aiming for perfection takes too much effort – but left too long and you end up with an unkept mess.

_Refactoring_ is like pruning. Adding functionality to a system starts off with planting new seeds of code. Functions start small, but over time they grow as they get called upon to do more things as yet more functionality gets added and they start to integrate with the rest of the garden.

To prevent our unkept mess, we refactor as we go. Fixing little shortcuts we took, tidying up functions that have grown too large, and pulling out common components so that the whole codebase doesn't get unwieldy.

Like your garden, you can often _see_ the overgrown areas without looking too hard, but we've also got tools to help us spot the less obvious issues. It's better to prune these problems with a little and often approach so that you don't need a huge clean up of an area just so that you can add a new plant.

**Weeding:** Weeds are different to the plants we prune. They're inevitable, but we have less control over where and when they appear. We accept that to grow a garden anywhere other than a lab-controlled environment, we're going to have to deal with some weeds.

Similar to pruning, the longer you leave weeds the more difficult it is to remove them as they grow stronger roots. A big difference is that you often don't notice weeds at first. They sneak up from below and strangle your plants.

In software systems we almost always rely on third party code that's not written or maintained by us. We could write everything ourselves, but where does it end? Should we write our own operating systems and build our own hardware? Accepting _dependencies_ is like accepting the inevitability of weeds.

Letting these dependencies go out of date as the maintainers add new features and fix bugs and security issues is like letting weeds grow. At first they start small – just a minor patch release here and there – but before you know it you're several major versions behind and getting back up to date takes a significant effort; just like if you left your flowerbed unweeded for a few months.

Like weeds, dependencies going out of date is a little less obvious until they become a problem. In recent years some nice tools have appeared to notify us and automatically apply updates, but in general dependencies are much further back in your mind compared to the plants you deliberately planted and want to keep pruned.

Weeding should be done little and often – just like pruning – to make sure the plants you want for your garden don't get stunted and overrun by problem species.

**Landscaping:** Landscaping is the heavy duty stuff for when you want to make big changes. This takes some dedicated time and effort to achieve, and you've got to live with the mess during the process.

The problems arise when you try to work on top of ground that hasn't been landscaped appropriately. If you wanted to add a shed to your garden you'd need to level the ground and add a treated timber base to keep the shed level and keep it off the damp ground. Omitting this would result in the shed timbers twisting over time and gaps and cracks will appear in the structure, while the base slowly rots away as it gets saturated with winter rains.

Landscaping is hard to do little and often because you're making changes to the fundamental structure of the ground. You could try to landscape on your weekends off, but for big projects you might be trudging through the mud for months on end, all the while the rest of the garden continues to need pruning and weeding to keep it under control.

People hate allowing for landscaping in software development. It's hard, messy and often no visible change in the system can be seen from the outside. But you can see it when you look at the code. Building on good foundations is critical for writing software where there's a desire for longevity. Just like the shed on damp ground, not building on top of good foundations leads to the things you build becoming brittle and damaged much more quickly than you want them to. You see this in software in the form of bugs and features taking an increasingly long time to develop.

You often need to repair this damage when it happens to prevent further knock-on damage. Rain entering your shed will start rusting your tools away, much like bugs may lead to data loss or corruption. These problems always seem to happen at just the wrong time.

---

Analogies can often go too far, So I'll leave it at that.

The important thing to understand is that while parts of software development can operate like a production line – just like you can make a little production line for potting a selection of new seeds – the system you deploy to the world is much closer to an ecosystem than a widget, so the processes you use to manage it must be well suited to this type of problem.

<span>Photo by <a href="https://unsplash.com/@igcorreia?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Ignacio Correia</a> on <a href="https://unsplash.com/?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>
