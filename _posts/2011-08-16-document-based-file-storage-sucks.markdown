---
layout: post
title: Document-based File Storage Sucks
meta: A document-based file storage system is useless for a notebook style app. A linear file-system would be much more appropriate.
---

# Document-based File Storage Sucks

I&rsquo;ve been doing a lot of thinking lately where I&rsquo;ve wanted to get ideas out of my head and on to something physical. 90&#37; of the time I&rsquo;m sat with a computer so some sort of notes app sounds like it should fit the bill.

## Wrong.

I happen to use [Simplenote](http://simplenoteapp.com) with the desktop companion app [Notational Velocity](http://notational.net). While it&rsquo;s a great service, it lacks the friendly and familiar user experience of a good old fashioned notebook.

In [work](http://cardiffstudents.com) I&rsquo;m coming to the end of one of the bigger projects we do so I wanted to think up ten things I could learn while working on the next projects. With [Notational Velocity](http://notational.net) I had to create a new file, think up a name for it and then remember exactly what I called it next time I want to access it.

<figure class="grid-1 right">
	<img src="/images/posts/notational-velocity-document-storage.jpg" alt="Screenshot of Notational Velocity which uses document-based storage" />
</figure>

Okay; so that&rsquo;s not really a big deal, but just a few of these small &lsquo;notes&rsquo; will make the file list in the sidebar pretty large. [Simplenote&rsquo;s](http://simplenoteapp.com) search or create feature is great, but I think **the whole notion of separate files just doesn&rsquo;t work for a notebook style app**.

## Linear File Storage

A notebook is so easy to use. You flip to the last-used page. If there&rsquo;s space, you write there. If not, you start on a new page. What could be easier?

I&rsquo;d love an app that doesn&rsquo;t have any visible file structure. I think the experience of a notebook could be enhanced with the paradigms we&rsquo;ve become accustomed to – like search and copy &amp; paste – while keeping the simplicity of a wad of bound paper.

<figure class="grid-3">
	<img src="/images/posts/notebook-app-sketch.jpg" alt="Mockup of a simple notebook-inspired app" />
</figure>

A fixed-size text area with some simple styling options and the ability to search would be more or less all I&rsquo;d need, along with the ability to move backwards and forwards through the notebook.

In terms of technical implementation, notes could be stored in some sort of wrapper file ([Day One](http://dayoneapp.com/) uses <code>Journal.dayone</code>), or as a bunch of single rich text documents in a user-determined folder. What&rsquo;s most important is that the user see&rsquo;s their notebook as a continuous stream of content – not a diary with one page per day, or one file per subject.

I really, really want an app like this. I&rsquo;d love to help someone build it, or gladly pay someone who already has. For now though, I think I&rsquo;ll be buying a [Moleskine](http://www.amazon.co.uk/Moleskine-Ruled-Notebook-13-21cm/dp/8883701127/ref=sr_1_1?ie=UTF8&qid=1313532410&sr=8-1).




