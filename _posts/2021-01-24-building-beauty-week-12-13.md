---
layout: post
title: "Building Beauty: Week 12 & 13"
---

# {{ page.title }}

## Studio

We’re back at it. This year focuses largely on our individual projects “in our community”. Obviously that’s quite tricky at the moment, but hopefully I’ll be able to integrate some sort of community collaboration into [my project idea](/2020/11/10/building-beauty-week-5#studio-individual-project).

The plan for this semester is to use the large-scale project as a way of working through 5 broad themes.

**Self**: The focus on self is on the realisation that the mindset, who we are, how we approach what we do, is an inseparable part of the process.

**Community**: Especially challenging and poignant given the pandemic. Trying to focus on working with others more than working for yourself.

**Space**: A little more of a deep dive compared to last semester. Couple of new exercises and tools in addition to what we did last semester.

**Making**: We don't separate design and construction. Always being in a making mindset. Trying to avoid abstract things. Get real as much as possible. So rare for an architect to show up to a site with materials early in the process.

**Wholeness**: Whatever we do this semester is part of something larger that's happening in the world; a shift in focus from looking at your project as a thing in its own little microcosm. It will hopefully end up with a life of its own.

We did an exercise in identifying needs in the community (in business-speak, articulating the demand rather than supply). This was fun, but a little disheartening. It’s easy to find these problems to solve, but many of them are quite unsolvable by an individual, or even a small group. Saachi had a great framework for approaching these challenges:

![Needs in the community](/images/posts/building-beauty/studio-needs-exercise.jpg)

> Any public space is defined by 3 sets of rules:
>
> 1. **Laws** and regulations
> 2. **Customs** and habitual ways of doing things (festivals, daily routines, etc)
> 3. **Conventions** which are determined through voluntary activity
>
> Try to figure out the spaces where **conventions** govern the behaviour of the space.
>
> If you want to change the structure of a bridge you have to tackle the **law**; cutting the bushes might be more on the **conventions** side.

This seems like a useful tool for building weight around the periphery of a problem; starting to build a community of people who care. After a while, once that community is strong enough, maybe you can start challenging the next level of complexity.

<hr>

Chris A gave a talk on pattern languages. When we're looking for problems to solve in the environment, we also need a clear structure on how to approach a solution to those needs. A Pattern Language (the book) provides a very clear model for how to approach defining a solution to problems or needs. Each pattern is a combination of narrative, words, imagery, research and connection to larger scale patterns that you likely have no control over, and also to smaller scale patterns that you do have control over. It helps you communicate ideas to other people.

<hr>

Saachi gave a talk on his work in communities, especially around interviewing. At a certain scale, everyone wants to “work with communities”. This often results in imposing on “community leaders” to tick boxes. People get suspicious and tired of it. To not fall into these patterns we must learn to *listen*, which is not a simple task. Even if you don't speak for an entire day, your inner voice is deafening. Listening means to quiet the inner voices.

<hr>

Sergio gave a talk on his implementation of a larger scale community project, tying together the talks from Chris and Saachi earlier in the week.

The project explored how construction heals both the land and the people using the space. The project team comprised of students with very different backgrounds – biology, architecture, marine engineering, etc – all vertically integrated around the project.

In Battle, the Pattern Language is the process of interaction between design team and users through face-to-face interviews. The aim is to gradually bring the conversation away from the "building program" and towards deep feeling. It's not about the specific project; it's about trying to find generic patterns that find the perfect generic form-context fit; the "school-ness of a school", "the lamp-ness of a lamp".

He then showed how they recorded interviews, which was pretty interesting. Each named “place” gets recorded along with its attributes. This helps extract the *feeling* of the space from the interviews. Places are indented if they belong to a larger space. This can all be visualised geometrically, which gives a sense of sequence of the space, and the relative sizes and importance of each space. After many interviews are complete, a synthesised version is compiled.

![Sergio's interview notes and synthesis format](/images/posts/building-beauty/sergio-interview-notes.jpg)

## Nature of Order

We’ve started Book 3, A Vision of a Living World. This book is essentially a collection of examples that show how the world could be if the ideas in Book 1 & 2 are followed.

We started the semester with a discussion of Belonging & Not Belonging. Alexander’s view on belonging is that it’s a function of control. If you have some control over a place you have some belonging.

Yodan gave a talk about his work related to boulevards as hulls of public space, and Muni gave a talk about his loooong project developing a nunnery in India. The highlight of the first couple of weeks for me though was [Bruno Postle’s](https://twitter.com/brunopostle) talk about his open source projects [Homemaker](https://bitbucket.org/brunopostle/urb/wiki/Homemaker) and [Topologise](https://bitbucket.org/brunopostle/urb/src/master/README_TOPOLOGISE.md).

Homemaker is a way of algorithmically generating structures for a given plot that are harmonious with some of the patterns from A Pattern Language (and some other criteria). The results are stunning.

![Homemaker evolution animation](/images/posts/building-beauty/homemaker-evolution-animation.gif)

This animation shows a single building, but the plot can be large enough for 10s or 100s of buildings and the buildings look exactly like they’ve been unfolded over time. Essentially, they are. The algorithm calculates scores for each building and rejects any that fall below a certain score until each building scores well.

The Pattern Language acts as a genetic code for the evolutions. The genetic code for these buildings is about the same size as a small protein like insulin; ~180 base pairs.

![Homemaker small town plot](/images/posts/building-beauty/homemaker-small-town-plot.jpg)

Topologise works at the level of an individual building. Starting with a cube, Topologise, using the same genetic code as Homemaker can transform it into a building.

![Topologise one-click house](/images/posts/building-beauty/topologise-one-click-house.jpg)

You can apply different “form languages” like a CSS stylesheet (currently only Georgian and North African), and failure cases of each pattern can be highlighted, giving designers real time feedback of how the house will work in reality. Of course, these are still only models, but it’s a fantastic improvement to the traditional CAD programs that offer no “real world” feedback during the design process.

![Topologise feedback](/images/posts/building-beauty/topologise-feedback.jpg)
