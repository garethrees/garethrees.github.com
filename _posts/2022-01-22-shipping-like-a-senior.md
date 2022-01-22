---
layout: post
title: Shipping like a Senior
meta: Six steps that differentiate senior developers
---

# {{ page.title }}

I’ve been having a few conversations with friends over the last year about what differentiates a senior developer, and it’s often quite difficult to put your finger on. I think one of the key day-to-day things that’s noticeable is not necessarily the end result that’s produced, but the journey taken to get there.

One of the items at the senior level of [our technical job roles](https://www.mysociety.org/about/careers/) matrix gets at this…

> Scopes and stages work into well-defined milestones to avoid a monolithic deliverable

…but only describes _what_ to do, not _how_ to do it.

Pilots have a pretty complex job, so they [prioritise their actions](https://www.franklinfaraday.com/how-to-deal-with-complexity-like-a-pilot-part-1/): *Aviate* (fly the plane and don’t crash); *Navigate* (fly in the right direction); *Communicate* (tell people where you are and where you’re going). Software is not so dissimilar. We’re dealing with loads of moving parts and trying to get them to work together, we’re trying to create something of value, and we’re working with others while doing it.

Along with writing raw source code (aviating), developing software, and many other types of knowledge work, have several little cognitive tricks that help us navigate and communicate our way through complexity.

Here’s how I think about it:

> **Shape ⤴ Scope ⤴ Sequence ⤴ Spike ⤴ Sparkle ⤴ Ship →**

## 🔮 Shape

[Shaping](https://www.garethrees.co.uk/2020/09/11/shaping-software-context-boundaries-language/) is about de-risking work by taking a somewhat vague sense of what to do into a *rough* but *solved* and *bounded* description that you can schedule with the confidence that you’ll complete it within the time you budget.

For bigger projects someone in more of a product manager role may do a significant portion of this, but it’s still really useful no matter how small the work to make sure you’ve got a clear idea of what constitutes a success.

## 🔎 Scope

Scoping is about figuring out the [orthogonal parts](https://rjs.medium.com/managing-product-development-by-integrating-around-concerns-77640bcde28d) of what you’re building. *Scopes are not tasks*, but more like an outline of the system, or the rooms of a house.

Scopes help you pick the best place to start within the shaped work, and help you continually prioritise the remaining work and assess progress as you move through it.

## 🧬 Sequence

Finding the [epicentre](https://basecamp.com/gettingreal/09.2-epicenter-design) – the scopes that deliver the core value of the work – is critical for being able to start in the right place and work on the parts of the project in the most effective order.

If we spend the majority of our time building incidental parts of the system before we get to the epicentre we’re really risking running out of time or hitting an unknown that jeopardises the entire project. Hitting a significant blocker in an incidental scope can often be worked around or ignored altogether, but if we can’t deliver the core value then none of the other things matter.

## 🪡  Spike

In all but trivial cases, much of what we build is new and unknown. When we encounter these unknowns, we want to sense-check our approach to uncover rabbit holes before we get too deep and [don’t want to take a different approach](https://en.wikipedia.org/wiki/Escalation_of_commitment) because we’ve already put so much work in.

To do this we’ll “[spike](https://en.wikipedia.org/wiki/Spike_(software_development))” (or prototype) the work – hack it together as quickly as we can to get a roughly working version to use and interact with. Once we’re confident that we can hook the main components together in a way that does what we want we can then finish off the work to a production standard.

## ✨ Sparkle

When we’re [over the hill](https://www.garethrees.co.uk/2020/07/05/tracking-work-through-knowns-and-unknowns/) and confident that we’re on the right track with what we’re building, we can finally add all the polish and finishing touches that we all love doing. We can finesse the language of the domain model, unpick our spike into well-factored methods, add edge-case tests and smooth out the UI.

Sparkles are the things that make us feel proud of our work, but it’s important that they support something that adds useful capability for the user. Otherwise they’re more like novelty tourist-tat that, while shiny, doesn’t really serve much purpose.

## 🚀 Ship

Shipping work is not just about getting the code merged, but creating a package for the work that’s as well considered as the work itself. Think about the experience of opening a new Apple product. The quality of the packaging, and the way everything fits inside it, all give you confidence that you’re opening a quality product.

Software development is no different. A Pull Request that contains a [logical set of commits](https://mysociety.github.io/coding-standards.html#improving-topic-branches-by-rewriting-history) with good [commit messages](https://mysociety.github.io/coding-standards.html#commit-messages) and a   coherent [overall description](https://mysociety.github.io/coding-standards.html#making-a-pull-request) with screenshots and a release plan, if appropriate, all give others confidence that they’re about to review a quality piece of work. This creates a low-friction collaborative environment, and much of the effort that goes in at this stage can be re-purposed to show [work in the open](/2018/07/10/book-notes-show-your-work/).

## 📢 Communicate after each step

Each step represents an opportunity to pause and communicate.

Communication isn't just about announcing progress (“I’ve done X”) but about *refocusing on the wider whole* rather than the in-the-weeds details (“I’ve done X; is it the right thing? Do I need to course correct? Is it actually going to work in the [situation](https://www.garethrees.co.uk/2020/03/13/why-does-situation-matter-more-than-what-customers-like/) we're designing for?”). If you’re not thinking about wholeness your product isn't going to be coherent, just a load of individual pieces.

Not all of this communication needs to be for the here and now. Great commit messages communicate with a future you or colleague. Descriptive pull requests with screenshots and gifs create a foundation for documentation and blog posts. Even when your communication is more temporal, you [don’t always have to wait](https://world.hey.com/jorge/don-t-block-yourself-a-remote-worker-super-power-7322c679) for input. The main purpose is creating good, calm situational awareness for yourself and the others that you’re working with.

Before communicating outwards consider communicating inwards with yourself. Reflect on the work and ask whether it serves its purpose for the stage you're at. Try to anticipate what questions and comments others may have. Self-reflection makes for better more articulate communication with others.

---

<small>Thanks to Lloyd Wheeler, Aaron Evans, Louise Crow and Sam Pearson for reviewing drafts of this post.</small>
