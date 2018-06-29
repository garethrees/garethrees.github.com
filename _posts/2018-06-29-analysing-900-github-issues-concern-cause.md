---
layout: post
title: "Analysing 900+ GitHub Issues: Concern + Cause"
---

# {{ page.title }}

**TL;DR:** I classified 900+ issues in just a few hours and ended up with another tool to make better decisions about how to prioritise work.

[Last time I wrote about GitHub gardening](/2018/04/24/foi-team-github-gardening) I mentioned I'd been using "feature area" labels to group issues around “concerns”:

![Alaveteli Pro Concerns](https://i.imgur.com/gk8n6ZV.png)

I've also been trying to categorise issues as one of “bug”, “improvement” or “enhancement”.

* **Bug:** Breaks expected functionality
* **Improvement:** Improves existing functionality
* **Enhancement:** Adds new functionality

Hat tip to Tony for this idea, taken from the “cause” attributes in [aegis](https://www.gsp.com/cgi-bin/man.cgi?section=5&topic=aecstate), an old source control system.

This has been helping us make better judgements when prioritising issues. In general, for example, the presence of a bug causes more pain than the absence of an enhancement. Its also useful for breaking down complex issues. On a few occasions I’ve been able to extract a “bug” issue and get a simple fix in for the immediate pain point, and then create an “improvement” or “enhancement” issue for future consideration.

This “concern” + “cause” classification can give us a surprising amount of information about the health from the _project’s_ – rather than the _codebase’s_ – point of view.

---

## Aside: What are “Concerns”?

The idea of [product “concerns”](https://medium.com/@rjs/managing-product-development-by-integrating-around-concerns-77640bcde28d) comes from [Ryan Singer](https://twitter.com/rjs) of Basecamp. Its similar to [Separation of Concerns](https://en.wikipedia.org/wiki/Separation_of_concerns) in programming. The value is that one concern can be worked on independently of another, making maintenance and changes easier.

![Concerns for a conference registration app](https://cdn-images-1.medium.com/max/1600/1*weBIUwhrmkCAN1z5V-8Lkg.png)

In his talk at Industry Conf 2018, Ryan went in to a bit more detail on how he starts thinking about [UI flows](https://signalvnoise.com/posts/1926-a-shorthand-for-designing-ui-flows) and then slices them in to concerns:

![Slicing concerns](https://i.imgur.com/50vAFfQ.jpg)

What’s neat about this is that it allows you to be explicit about where the value is in your application. In the example conference registration app, its clearly the buying of tickets. Concerns like exports and user management are nice, but not essential.

![Where the value is in a conference registration app](https://cdn-images-1.medium.com/max/1600/1*mt3BE5mWbx1S2LLlgIBlCQ.png)

In Alaveteli, our main areas of value are in creating and managing FOI requests, and our database of public bodies.

---

The problem with trying to do any sort of analysis is actually classifying a huge backlog of issues to get a full picture. Newer issues have been classified with this labelling scheme, but lots of old issues were lacking information.

I've been pondering this for a while, and recently I came up with a way of doing this that only took a couple of hours (rather than days, if going through them in the GitHub interface).

First, I exported all issues in to a CSV, along with any labels that matched one of the “cause” labels, or that started with `f:` (our “concerns”, or “features”):

![Export of Alaveteli Issues](https://i.imgur.com/97IAQjV.png)

The title was generally enough to categorise the problem, but it was easy enough to dig in to an unclear issue by using the exported URL.

It was then pretty easy to tab-complete labels where missing:

![Tab completing labels](https://i.imgur.com/7wad3lE.png)

It took a couple of hours to get through the issues, but it didn't feel too arduous doing it over a few days. It would have been soul-destroying to have to go through each issue in the GitHub Issues interface.

I then wrote an uploader that syncs the labels from a CSV export of the spreadsheet to the issues in GitHub.

![Automatic label sync](https://i.imgur.com/AdfAluk.png)

With all the issues categorised, I could now do a little analysis! I wanted to look at the distribution of “causes” are in each “concern”. Doing this would give us a picture of whether a concern is causing users lots of frustration because it keeps breaking (lots of `bug`s); whether what we’ve got is working, but not that well (lots of `improvement`s); or whether we’re not handling possible user journeys at all (lots of `enhancement`s).

![Analysis now](https://i.imgur.com/ETYOLV2.png)

The most striking thing to me is that `f:request-management` has _lots_ of issues labelled `bug`. We're not aiming for zero bugs, but since request management is a _key_ value area in Alaveteli it’s hard to imagine the amount of bugs here not causing real user frustration.

The real value here for me is that I’ve got another tool to help make tradeoffs when we’re prioritising work. Given the current analysis, an “enhancement” in `f:user-profiles` (a lower value concern) would have to put up quite a fight to get priority over a “bug” in `f:request-management`, but maybe in a year’s time when we’ve fixed a load of bugs the picture would be different enough to make a better case for some work on `f:user-profiles`:

![Analysis 1 year on](https://i.imgur.com/3eWOH2D.png)

---

I'm not set on the exact concern labels yet. An issue often spans two or more concerns, which seems like a bit of a smell. A good tool should [do one thing and do it well](https://en.wikipedia.org/wiki/Unix_philosophy), so if we’re seeing issues that span several concerns it may mean that part of the application is trying to do too much at once, and confusing our users in the process.

Similarly, sometimes its been tricky to decide between the “cause” labels.

Still, I've been finding the concern + cause pairing really useful for improving how I compare issues against each other.

---

I’ve [pushed the code to GitHub](https://github.com/garethrees/cause-concern-triage) if anyone fancies trying this out. Please be aware that its not tested, so I’d recommend reviewing it before you run the `sync` script.
