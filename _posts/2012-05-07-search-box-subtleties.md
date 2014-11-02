---
layout: post
title: Search Box Subtleties
meta: Seach box design on World Vision Micro Group Giving
---

I recently added a new interface to the [Group Giving](http://worldvisionmicro.org/groups) section of [World Vision Micro](http://www.worldvisionmicro.org).

The first step a donor takes is browsing or _searching_ for a group to sponsor.

## Progressive Enhancement

I used some progressive enhancement to add some extra nicities in modern browsers. The enhancements make the donor experience a little nicer, but the interface is still completely usable if their browser doesn't support the newer CSS styles.

**Chrome**

!['Group Giving progressive enhancement example in Chrome'](/images/posts/micro-group-giving-search-chrome.jpg)

**Internet Explorer 7**

![Group Giving progressive enhancement example in IE7](/images/posts/micro-group-giving-search-ie7.jpg)

The progressive enhancements are:

- Gradient background on the form buttons
- Placeholder text in the search box
- CSS border arrow leading the donor in to the search section
- CSS dotted border at end of search section

## Contextual Micro-copy

Initially the donor is presented with text explaining what to do with the search box.

> Search by group name or leader name

![Group Giving search input before submission](/images/posts/micro-group-giving-search-input-before.jpg)

Once the donor has actually made the search, the user input is highlighted and the copy is changed.

> You searched for:

![Group Giving search input after submission](/images/posts/micro-group-giving-search-input-after.jpg)

This micro-copy helps provide feedback to the donor by explaining that the application has done what they requested. Since the search is performed with a `GET` request and a query parameter, the search URL can be shared with others. The higlight reminds the donor (or the recipient of a shared search URL) why they are seeing a limited set of results.
