---
layout: post
title: "Book Notes – Shape Up"
---

# {{ page.title }}

## 1. Introduction

Building the right thing: Competing Against Luck

This book is about the risk of getting stuck, the risk of getting bogged down with last quarter’s work, wasting time on unexpected problems, and not being free to do what you want to do tomorrow.

## 2. Principles of Shaping

Wireframes are too concrete – no space for creativity and harder to estimate
Words are too abstract – no clear picture and no boundaries

Properties of shaped work:

* It's rough
* It's solved – clear direction; no open questions
* It's bounded – what not to do; clear appetite

Steps to shaping:

* Set boundaries – appetite + problem definition (job)
* Rough out the elements
* Address risks and rabbit holes
* Write the pitch – summarise the problem, constraints, solution, rabbit holes, and limitations

## 3. Set Boundaries

The conversations we have are going to be entirely different if people think we’re talking about a small improvement or a major redesign.

Boundary is set when you have: raw idea, an appetite, and a narrow problem definition

Set appetite:

* Is this something worth a quick fix if we can manage?
* Is it a big idea worth an entire cycle?
* Would we redesign what we already have to accommodate it?
* Will we only consider it if we can implement it as a minor tweak?

Fixed time, variable scope

Good is relative: We can only judge what is a “good” solution in the context of how much time we want to spend and how important it is. Compare to baseline.

Responding to raw ideas: “Interesting. Maybe some day.”

Narrow down the problem: At what point specifically does someone’s current workflow break down without this thing they’re asking for?

Watch out for grab-bags: redesigns and refactorings.

* Bad: “Redesign the Files section.”
* Better: “We need to rethink the Files section because sharing multiple files takes too many steps.”
* Questions: What’s not working? In what context are there too many steps? What parts of the existing design can stay the same and what parts need to change?

## 4. Find the Elements

Aim to be concrete enough to make progress on a specific solution without getting dragged down into fine details.

* Where in the current system does the new thing fit?
* How do you get to it?
* What are the key components or interactions?
* Where does it take you?

Breadboarding: Define the key components and connections without specifying an interface design

* Places
* Affordances
* Connection lines

Fat marker sketches: made with such broad strokes that adding detail is difficult or impossible.

Elements are the output: Aim to narrow them to specifics rather than e.g. "monthly calendar".

At this stage, we could walk away from the project. We haven’t made any commitments or promises about it. What we’ve done is added value to the raw idea by making it more actionable. We’ve gotten closer to a good option that we can later lobby for when it’s time to allocate resources.

## 5. Risks and Rabbit Holes

Different categories of risk:

* Well shaped: High probability of hitting budget
* Poorly shaped: Long right tail: low but non-zero probability of going over

Looking for rabbit holes:

Walk through a use case in slow motion. Given the solution we sketched, how exactly would a user get from the starting point to the end?

* Does this require new technical work we’ve never done before?
* Are we making assumptions about how the parts fit together?
* Are we assuming a design solution exists that we couldn’t come up with ourselves?
* Is there a hard decision we should settle in advance so it doesn’t trip up the team?

As shapers, we’re thinking less about the ultimate design and more about basic quality and risk.

Cutting back:

Mention nice-to-haves explicitly – start from the assumption that the feature is valuable without them.

Inviting an expert:

In software, everything is possible. Instead of asking “is it possible to do X…” we want to ask “is X possible in a 6-week project.”

Talk through the constraints of how this is a good solution given the appetite, so they’re partners in keeping the project at the size you intend. And emphasize that you’re looking for risks that could blow up the project.

Try to keep the clay wet. Rather than writing up a document or creating a slideshow, invite them to a whiteboard and redraw the elements as you worked them out earlier, building up the concept from the beginning. Once you’ve covered the work you already did, open it up and invite them to the shaping process. Having seen this concept, do they have any insights about how to drastically simplify or approach the problem differently?

De-risked and ready to write up:

At the end of this stage, we have:

* the elements of the solution
* patches for potential rabbit holes
* fences around areas we’ve declared out of bounds

## 6. Write the Pitch

* lobby for resources
* collect wider feedback
* capture the idea for when the time is more ripe

The purpose of the pitch is so that the people who schedule projects can make an informed bet.

* Problem – the job, based on the raw idea
* Appetite – time to spend and boundaries
* Solution – the core elements
* Rabbit holes – potential risks and nice-to-haves
* No-gos – boundaries

Ingredient 1. Problem:

It’s critical to always present both a problem and a solution together.

Without a specific problem, there’s no test of fitness to judge whether one solution is better than the other. The solution might be perfect, but what if the problem only happens to customers who are known to be a poor fit to the product?

We want to be able to separate out that discussion about the demand so we don’t spend time on a good solution that doesn’t benefit the right people.

The best problem definition consists of a single specific story that shows why the status quo doesn’t work. This gives you a baseline to test fitness against.

Ingredient 2. Appetite:

Stating the appetite in the pitch prevents unproductive conversations. There’s always a better solution. The question is, if we only care enough to spend two weeks on this now, how does this specific solution look?

Ingredient 3. Solution:

A problem without a solution is unshaped work. Giving it to a team means pushing research and exploration down to the wrong level, where the skillsets, time limit, and risk profile are all misaligned.

Help them see it:

* Hack fat-marker sketches in to existing UI
* Add just enough extra detail to breadboards to make them recognisable as interfaces
* Cleaned up fat-marker sketches with annotations or call-outs

Ingredient 4. Rabbit holes:

Sometimes addressing a rabbit hole just requires a few lines of text.

Ingredient 5. No Gos:

Make things explicit when its likely they'd cost more than the appetite.

## 7. Bets Not Backlogs

The growing pile gives us a feeling like we’re always behind even though we’re not.

Ideas go stale

Pruning and navigating backlog costs time

Bet on a couple of pitches every few weeks

People and teams keep their own lists; tend to only pitch top priorities. Helps spread prioritisation around the org. 1-1s get people talking about their priorities and potential solutions

This way the conversation is always fresh.

## 8. Bet Six Weeks

Overlapping projects turns project planning into a frustrating game of Calendar Tetris. Working in cycles gives a standard project size both for shaping and scheduling.

Two-week sprints are too short to get meaningful projects done and increase planning overhead.

Cycles do need to be long enough to see the end. Makes people make trade offs and you know a fresh project will come to avoid a slog.

End of a project is worst time to plan as everyone is tired and trying to get stuff finished.

Two week cool down gives people time under their own control to fix bugs, make pitches or experiment.

Fixed team types (number of programmers and designers) and project types (big batch and small batch) to standardise the way to think about capacity.

Betting table is a meeting during cool down to decide on pitches for the next cycle.

Hour or two call. Everyone familiar with pitches from background reading in advance on their own time


Between everyone present, there’s knowledge of who’s available, what the business priorities are, and what kind of work we’ve been doing lately. All of this feeds into the decision-making process

No extra sign off or meddling with the plan later because highest people are there.

The meaning of a bet:

The pitch defines a specific payout that makes the bet worth making.

We’re not trying to optimize every hour of a programmer’s time. We’re looking at the bigger movement of progress

a smart bet has a cap on the downside - don’t automatically extend

When you pull someone away for one day to fix a bug or help a different team, you don’t just lose a day. You lose the momentum they built up and the time it will take to gain it back.

Circuit breaker eliminates risk of runaway projects

A hard deadline and the chance of not shipping motivates the team to regularly question how their design and implementation decisions are affecting the scope.

Bugs:

* Use cool-down
* Make a pitch
* Bug smash cycle (around holidays)

The key to managing capacity is giving ourselves a clean slate with every cycle.

Betting table questions:

* Does this problem matter right now?
* Is the appetite right?
* Is the solution attractive?
* Is this the right time?
* Are the right people available?

> We’ve seen some other companies use a different model where instead of assigning the projects to people, they let the team members choose which projects they want to work on.

TODO: What about iterations app?

At the end of the betting table someone announced the pitches decided on for the next cycle of work

## 9. Hand Over Responsibility

Assign projects, not tasks

We want the project to stay “whole” through the entire process so we never lose sight of the bigger picture.

They will have full autonomy and use their judgement to execute the pitch as best as they can.

Done means deployed

Kick off by posting the pitch and having a kick off call.

Expect a bit of silence in the first three to five days of a project as the team figures out the project from their point of view. Don't nag for progress here.

Imagine vs discovered tasks:

* Imagined tasks are the tasks you think you need to do before you actually start
* Discovered tasks are the tasks that you discover you need to do when you're actually doing the work

You can't find out the discovered tasks before you even start – there are always unknowns.

## 10. Get One Piece Done

Don't try to plan all the tasks out in the first week and then try to integrate all the pieces at the end of the cycle. Instead, aim to make one small piece – front and back end – demoable early.

The team should work on the same scope at the same time, integrating front and back end. Either on their own are useless until integrated, so get one scope "done" before moving on to the next.

The pitch should inform foundational modelling direction so that programmers can get started without having to wait for designers to finish front end pieces.

Designers should implement affordances first so that programmers can integrate with them. They can add polish in parallel. Visual styling is important in the end product, not in the early stages. The same is true for backend work. You might add a controller that renders a template with mock data, or just wire up the routes to simulate navigation flow. Take turns layering in UI, code, and styling to the app.

Pick where to start:

* Should be *core* – is valuable even if its the only thing that gets done
* Should be *small* – builds momentum early
* Should be *novel* – reduces uncertainty

## 11. Map the Scopes

Organise by structure, not by person, so that you can see the big picture of how the _project_ is progressing.

In product development we're usually building something that didn't exist before, you need to figure out the scopes.

As tasks emerge, they can be grouped into scopes. The scopes reflect the meaningful parts of the problem that can be completed independently and in a short period of time – a few days or less.

Scopes become the language of the project (Domain Driven Design: Ubiquitous Language). Makes it easier to talk about progress at a higher level than the task-level details.

Scope mapping isn't planning – you need to get your hands dirty to find them.

Three signs indicate when the scopes are right:

* Important areas aren't hidden in the details
* The language helps conversations to flow better
* You know where to put new tasks

Three signs indicate the scopes should be redrawn:

* Completing tasks doesn't give a feeling of completing the scope
* The name isn't domain or project specific (e.g. file "bugs" under the scope that breaks, not under a "bugs" list)
* It’s too big to finish soon

Types of tasks and scopes:

* Layer Cake: Similar amount of front and back end code. Group in the same scope.
* Iceberg: Very imbalanced ratio of front to back end code. Keep simple area as one scope and split complex area in to multiple scopes. Always question whether icebergs need to be so complex.
* Chowder: Always a few tasks that don't fit into scopes, but always question. Shouldn't be more than 5 tasks
* Nice-to-haves: Mark with ~

## 12. Show Progress

Hard to show absolute progress with only tasks because they only emerge during development. To-do lists grow as the team makes progress.

Estimates are inaccurate, especially for work that the team has never done before. “4 hours, or maybe 3 days” isn't meaningful.

Work is like a hill:

* Push uphill to discover tasks and get from unknown to known
* Work on tasks downhill to get from known to done

Place each scope on the hill to enable good approximations of progress: "Edit Draft is on the downhill".

Managers can scan for scopes that don't move much to get a sense of what's stuck. Conversation becomes more about the work than the person: "What can we solve to get this over the hill?"

Stuck scopes might be a case of scopes that are too big to finish soon; refactor them in to separate scopes if this is the case.

Avoid things sliding back down the hill by making sure there's enough _implemented_ before saying that you're at the top of the hill.

Use hills to sequence the work. Tackle the scariest unknowns first – the stuff you haven't built before – as there's more risk. If you get to the end of the cycle and there are only a few tasks left but they're all stuff you know you can knock out quickly, there's less risk of spending some extra time on getting it done.

## 13. Decide When to Stop

There’s always more work than time. Shipping on time means shipping something imperfect.

It helps to shift the point of comparison. Instead of comparing up against the ideal, compare down to baseline – the current reality for customers.

The circuit breaker helps teams make trade-offs. Teams must be given authority to cut scope. Cutting scope isn't cutting quality, it just means adding less capability. The things that do get build should be good quality.

It takes significant energy to question and cut scope – we call it scope _hammering_ to reflect that.

Scope hammering questions:

* Is this a “must-have” for the new feature?
* Could we ship without this?
* What happens if we don’t do this?
* Is this a new problem or a pre-existing one that customers already live with?
* How likely is this case or condition to occur?
* When this case occurs, which customers see it? Is it core – used by everyone – or more of an edge case?
* What’s the actual impact of this case or condition in the event it does happen?
* When something doesn’t work well for a particular use case, how aligned is that use case with our intended audience?

The act of prefixing tasks with ~ is an act of scope hammering – usually they don't end up done.

To extend a project all the existing work must be downhill, and all incomplete must-haves can't be hammered in to nice-to-haves.

## 14. Move On

Be careful to avoid knee-jerk reactions after shipping new features. There's always some negative feedback, or extra feature requests.

Stay debt free. These are just raw ideas, so should be well shaped and placed on the betting table before getting allocated to a cycle.

## Conclusion

Main concepts:

* Shaped versus unshaped work
* Designing at the right level of abstraction
* Setting appetites instead of estimates
* Concepting with breadboards and fat marker sketches
* Making deliberate commitments—bets— instead of feeding the machine
* Choosing the right cycle length (six weeks)
* A cool-down period between cycles
* Breaking projects apart into scopes
* Downhill versus uphill work and communicating about unknowns
* Scope hammering to separate must-haves from nice-to-haves

## How to Begin to Shape Up

* One six-week experiment: Focus on shaped work, deliberate allocation and variable scope.
* Shaping first: Practice shaping to give teams clear work to highlight allocation problems.
* Cycles first: Extend cycle time to give project teams more room to breath.
* Build your muscle: Practice scope hammering and shipping on time to get project teams used to it.
* Focus on the macro: Focus on what gets shipped, not maximising people's allocated time.
