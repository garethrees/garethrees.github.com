---
layout: post
title: What should we work on next?
---

# {{ page.title }}

[Alaveteli](http://alaveteli.org/) is a large, long-running project with a sizeable history of bug reports, improvements and feature suggestions – and a fairly constant stream of new ones. In short, we have ~1200 open GitHub issues **(things to improve)**.

As a small team we're only able to do a small fraction of the things to improve, so picking the ones that will have most impact is vital to make the best use of our time.

Prioritising this many options is impossible – and having [a huge backlog is demotivating](/2018/04/24/hopper-vs-roadmap/) – but there are some great ideas hidden in the noise.

<details>
  <summary>
    Sea of Possibilities
    <img src="/images/posts/what-should-we-work-on-next/sea-of-possibilities.jpg" />
  </summary>
  <p>
    We try to <a href="https://mysociety.github.io/coding-standards.html#committing-code-and-working-with-repositories">ticket everything</a> at mySociety so that we can work asynchronously and <a href="https://en.wikipedia.org/wiki/Getting_Things_Done#Perspective">get things out of our head</a>. This makes for a <em>lot</em> of tickets.
  </p>
  <p>
    As a product manager its really difficult to see which of these are most valuable to users.
  </p>
</details>

<details>
  <summary>
    Group by Concern
    <img src="/images/posts/what-should-we-work-on-next/group-by-concern.jpg" />
  </summary>
  <p>
    <a href="/2018/06/29/analysing-900-github-issues-concern-cause/">Grouping issues by <strong>concern</strong></a> really helps to make a big initial step to reducing the cognitive burden.
  </p>
  <p>
    Grouping issues by concern lets you at least compartmentalise all this noise so that you’ve got some “shape” to the problem. Its much easier to think “How would I make our request management features better?” compared to “Which of these 1200 issues is most important?”.
  </p>
  <aside>
    <p>
      Even on an existing project, it was fairly easy to figure out our main feature areas. We've got some issues where there are overlaps, but I'm starting to think that an overlap may be a sign of confusion in the product.
    </p>
    <p>
      You can also add some extra resolution here by scoping issues by <a href="/2018/08/12/bug-improvement-enhancement/">bug, improvement or enhancement</a>.
    </p>
  </aside>
</details>

<details>
  <summary>
    Actionable Pitches
    <img src="/images/posts/what-should-we-work-on-next/actionable-pitch.jpg" />
  </summary>
  <p>
    The next step is to figure out which of these issues are ready to work on.
  </p>
  <aside>
    <p>
      This really clicked for me when I asked Ryan Singer about <a href="https://businessofsoftware.wistia.com/medias/lc2igd99yk">What makes a pitch actionable?</a> in a Business of Software hangout. Question at around 46:30.
    </p>
  </aside>
  <p>
    To do this, look for those that have a described <em>problem</em> and a proposed <em>solution</em>.
  </p>
  <p>
    Without a <a href="https://demandthinking.com/episodes/2017/7/23/episode-1-think-you-might-be-building-the-wrong-thing-youve-misinterpreted-demand">clear demand</a> then there's probably no real value in solving the problem. Issues of this nature fit in to the “Wouldn't it be nice if…” bucket.
  </p>
  <p>
    Without a proposed solution we can't make a good decision on whether completing the issue is valuable. We can't guess at how much effort is involved if we don't know what we're trying to achieve – so we can't decide whether the cost is worth it – or whether we can even solve the problem in a satisfying way at all.
  </p>
  <aside>
    <p>
      There will almost certainly be issues that you <i>know</i> are important, but don't have a proposed solution. These may be frequently occurring bugs, or some form of demand that you keep hearing over and over.
      The best thing to do here is assign the issue with a time-boxed allowance for coming up with a solution. This way you can get some more information each cycle, but without running in circles with it.
      Hopefully a round or two of investigation will lead to either a workable solution, or confidence in dropping the issue altogether.
    </p>
  </aside>
</details>

<details>
  <summary>
    Prioritise What's Core
    <img src="/images/posts/what-should-we-work-on-next/whats-core.jpg" />
  </summary>
  <p>
    By this point the picture should be getting really clear; only a handful of actionable issues will exist for each feature area.
  </p>
  <p>
    It may even be obvious which to pick, but if not we can ask <strong>“What’s core?”</strong> to reduce the options further. The concern groupings we made earlier help to make this question more concrete. Some of the concerns will be the key functionality that the app was specifically made for. Others will be support features, or extras that provide some added value.
  </p>
  <p>
    We don't necessarily have to work on “core” issues all the time, but asking this helps to give an indication of whether you'll be helping 3% or 30% of users.
  </p>
</details>

<details>
  <summary>
    Allocate to Cycle
    <img src="/images/posts/what-should-we-work-on-next/allocate-to-cycle.jpg" />
  </summary>
  <p>
    Now its just a case of making a call from the <a href="/2018/04/24/hopper-vs-roadmap/">items in your hopper</a> and allocating some work based on the time we have available. If an issue doesn't get picked, it can always be evaluated for the next cycle.
  </p>
</details>

None of this means that everything we pick is going to be the _most_ impactful out of the whole pool of things to improve. We'll miss some that aren't actionable, or maybe we'll pick some that just don't work out as we'd expected.

What we _are_ doing is maximising our chances of creating _some_ value by shipping the things we choose to work on. **Concerns** help compartmentalise the things to improve, and make better tradeoffs when we can't do everything we'd like. **Actionable issues** help avoid running in circles around an unclear solution, and ensuring the things that we work on are going to create real value for _someone_.

<details>
  <summary>
      Strategy is a process that goes on 24/7, not “an event” followed by implementation. Each cycle we'll build a better idea of what to focus on by getting feedback on what we ship, and by talking to users about situations they were in when they use our tools.
  </summary>
  <p>
    <img src="/images/posts/what-should-we-work-on-next/clayton-christensen-strategy.jpg" />
    – <a href="https://www.youtube.com/watch?v=Ei57yFEljrI">Clayton Christensen: Management</a>
  </p>
</details>

This has largely been inspired by [Ryan Singer's](http://www.feltpresence.com/) recent writing and talks about [Basecamp's](https://basecamp.com/) product management process.
