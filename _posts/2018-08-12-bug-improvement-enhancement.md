---
layout: post
title: Bug; Imrovement; Enhancement
---

# {{ page.title }}

I've been using three labels to [classify issues](/2018/06/29/analysing-900-github-issues-concern-cause/) to help prioritise them against one another.

Hat tip to [Tony](https://twitter.com/tmtm) for inspiring this idea by telling me about the “cause” attributes in [aegis](https://www.gsp.com/cgi-bin/man.cgi?section=5&topic=aecstate), an old version control system.

<h2><span style="background-color:#ee0701;color:#fff;padding:2px 4px;"><code>bug</code></span></h2>

A [bug](https://github.com/mysociety/alaveteli/labels/bug) means something is broken, _preventing a customer use the capability_ the feature is providing them.

Not all bugs are worth solving – some may happen in really rare edge cases only once or twice a year – but I tend to give bugs a lot of weight. If our solution is broken, then we're breaking the promise we made to help a customer in that situation.

<h2><span style="background-color:#c5def5;padding:2px 4px;"><code>improvement</code></span></h2>

[Improvements](https://github.com/mysociety/alaveteli/labels/improvement) are _changes_ to the way we do something we already do. This might mean improving [performance](https://github.com/mysociety/alaveteli/labels/f:performance), or maybe tweaking a [design](https://github.com/mysociety/alaveteli/labels/t:design) to make an affordance clearer.

Improvements are tricky to prioritise as its difficult to know when something that already exists is “good enough”.

<h2><span style="background-color:#c2e0c6;padding:2px 4px;"><code>enhancement</code></span></h2>

An [Enhancement](https://github.com/mysociety/alaveteli/labels/enhancement) provides entirely new capability for a situation that we don't currently have a solution for.

Enhancements mean adding complexity to the software – you're adding _more stuff_ – so should fight hard to get included in the product.

## Writing Issues

As well as a prioritisation tool, these labels have helped to re-scope issues I've written or encountered.

When defining a solution to a bug report, for example, its easy to start thinking about how the current design could do with some work, or a more elaborate fix than strictly necessary. This leads to delays in fixing the bug for users.

Instead, I try to split the issue in to several issues of the above classifications.

For example, a recent bug report was filed where clicking a particular button while a particular process was running would lose some data. The bug report was well specified, but the solution could have easily expanded.

The simple fix to the _bug_ report was disabling the button until it was safe to allow the user to click it. This was a little unsatisfying, as doing this doesn't really explain _why_ it has been disabled. Worse, we didn't have a disabled button style for that section of the app.

Still, disabling the button closed the _bug_ issue and prevented any further data loss.

I then created two further issues:

* An _enhancement_ to add some `disabled` button styles to that part of the app;
* An _improvement_ to explain why we were disabling the button in some situations, and to apply our improved styling.

These new issues can now fight against others for prioritisation.

Chances are, the situation will come up so rarely that we won't need to tackle either – at least in relation to the original bug report.

Scoping issues with these “causes” helps to separate out the critical work from the nice-to-haves, and produce clearer issues that are less likely to consume more time than they're worth.
