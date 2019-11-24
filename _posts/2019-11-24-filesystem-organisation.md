---
layout: post
title: Filesystem Organisation
---

# {{ page.title }}

Over the years I've tried many ways of keeping my filesystem organised.

One was based on Getting Things Done…

![GTD-based filesystem](/images/posts/filesystem-organisation/gtd-filesystem.jpg)

…which took a lot of upkeep and moving things around.

After this I moved on to organising by "project" or "client", with a separate `~/Code` folder to keep that separate from incidental files. This was okay, but I often ended up wondering where I'd put files. Sometimes the files were about higher-level ideas across a few projects etc, so I was never that sure on where to start looking.

More recently I've just allowed files to accumulate in `~/Downloads`, with the odd folder in `~/Documents` that groups some related files. Day to day this isn't too bad, but gets unwieldy over time, and makes it quite difficult to find older documents and notes.

I've recently added some automation that helps reduce the pains of a single-bucket approach, but with minimal extra effort required on my part to do any frequent organisation.

## Overview

Here's a slimmed-down overview of my home folder:

```
$ tree -dL 1 ~
/Users/gareth
├── Desktop
├── Downloads
├── archive
├── doc
├── screenshots
├── src
└── tmp
```

I've edited this listing to just the key directories of note for this post.

The general flow of files is that they start off in `~/Desktop` or `~/Downloads`, automatically get cleaned up in to to `~/doc` once a month, and then every six months or so I'll scan through `~/doc` and move files to the `~/archive`.

## Temporary Files

For files that I know I only want to use for an extremely limited amount of time, I'll dump them in `~/tmp`. I usually destroy files here once I'm finished – generally they're just some sample data for reading in to a [`pry`](https://pryrepl.org/) prompt. This will soon be automated to clear out every restart.

## Code

Code lives in its own folder (`~/src`) as I find mixing source code and documents too confusing.

I used to just clone everything directly in to `~/src`, but after a while this ended up growing too large to manage, so now repos are cloned into a `username/project` folder, e.g. `~/src/mysociety/alaveteli`. This may need re-assessing if I start doing more work that spans other source hosting sites, but currently most things I need just use GitHub.

## Screenshots

Screenshots also have their own folder (`~/screenshots`). I frequently use screenshots when writing documents, GitHub issues, or for pasting in to chat, so I like having these to hand. I keep the screenshots folder in the Dock, sorted by Date Modified so that I can easily drag the most recent screenshots in to the application I'm using.

I use Date Modified so that any annotations I make to screenshots push the file up to the front of the Fan.

![Screenshots folder in the Dock](/images/posts/filesystem-organisation/screenshots-dock-fan.jpg)

![Screenshots folder settings](/images/posts/filesystem-organisation/screenshots-dock-settings.jpg)

## Current Work

For files other than source code, I'll generally just create them in `~/Desktop` or `~/Downloads`. I tend to go for `~/Desktop` for files I know I'll work on over a few days or weeks, and `~/Downloads` for a file that's just for today and tomorrow. `~/Downloads` also accumulates all the junk from web browsers and other apps.

Like `~/screenshots`, I keep `~/Downloads` in the Dock in a Fan view, but sorted by Date Added. This makes for quick access to files I've just downloaded or created, but maintains a consistent order. If I end up editing a file in `~/Downloads` over the course of a few days, I'll remember the filename and use [Alfred](https://www.alfredapp.com/) to open it, so I don't want it continually popping back to the front of the Fan each time I save it.

![Downloads Dock Fan](/images/posts/filesystem-organisation/downloads-dock-fan.jpg)

![Downloads Dock Settings](/images/posts/filesystem-organisation/downloads-dock-settings.jpg)

## Older Work

At the start of every month, anything in `~/Desktop` and `~/Downloads` is [automatically moved](https://github.com/garethrees/dotfiles/blob/master/script/LaunchAgents/uk.co.garethrees.clear-desktop-downloads.plist) to a [dated folder](https://github.com/garethrees/dotfiles/blob/master/bin/doclinks) in `~/doc`.

If I'm searching for a file, I can usually remember roughly when I was working on it, so organising this way is great because it can be completely automated.

```
$ tree -dL 1 ~/doc
/Users/gareth/doc
├── 2019-04
├── 2019-05
├── 2019-06
├── 2019-07
├── 2019-08
├── 2019-09
├── 2019-10
├── current -> /Users/gareth/Downloads
└── previous -> /Users/gareth/doc/2019-10
```

This adds a layer of organisation to the files that have accumulated, but still allows me to easily view them all as a big bucket by just opening a few directories.

![Doc Expanded](/images/posts/filesystem-organisation/doc-expanded.jpg)

For me, monthly directories work best, but you could use daily or yearly if you create more or fewer files.

For easy access I also keep `~/doc` in the Dock. List view makes it easy to quickly scan through every folder. Instead of Date Modified I sort by Name so that the order is consistent, with recent directories appearing closer to the Dock.

![Doc Dock List](/images/posts/filesystem-organisation/doc-dock-list.jpg)

![Doc Dock Settings](/images/posts/filesystem-organisation/doc-dock-settings.jpg)

This approach was inspired by Leah Neukirchen’s [Keeping your home clean with "mess"](http://leahneukirchen.org/blog/archive/2006/01/keeping-your-home-clean-with-mess.html).

## Archive

While the automation helps me not have to think too much about organisation on a day-to-day basis, every now and then I'll spend an hour scanning through `~/doc` and moving files to `~/archive`.

I could leave everything in `~/doc` perpetually, but that has a few downsides for me.

1. I usually want to separate out stuff _I've_ written or worked on from "reference" material (e.g. podcasts or saved articles).
2. Sometimes a structure can emerge, so I want to archive these together.
3. I currently have a single machine for work and personal use, so I want to end up with personal files separated from work stuff.

I've tried a few different approaches to `~/archive`, but I've settled on a simple strategy of splitting on `home` and `work`. Within each, I have three directories: `doc`, `lib` and `ref`.

```
$ tree -dL 2 ~/archive
/Users/gareth/archive/
├── home
│   ├── doc
│   ├── lib
│   └── ref
└── work
    ├── doc
    ├── lib
    └── ref
```

> I usually want to separate… "reference" material (e.g. podcasts or saved articles).

I move this type of file to `ref`. Sometimes I find it tricky to decide between `home` and `work` when there's an overlap (e.g. some sort of programming cheatsheet), but I generally err towards `home` unless its absolutely clear that I'd only want the file in a work context.

If there's a source that I save a lot from (say, a particular podcast) I'll create a folder inside `ref`, but otherwise I just drop files in at the top level. I usually [slugify](https://github.com/garethrees/dotfiles/tree/master/script/Services/slugify.workflow/) them, and [prefix the filename with the Date Created](https://github.com/garethrees/dotfiles/tree/master/script/Services/date2name.workflow) so that I have some idea of when the file was relevant to me.

> Sometimes a structure can emerge…

In some of my previous systems I found it too frustrating trying to organise files in to neat folders on a day-to-day basis. Its been much easier to review several month’s worth of files and group related things together if a general theme is emerging.

I use `lib` for files grouped by subject matter, [rather than by source](https://peelarchivesblog.com/2015/08/26/how-do-archivists-organize-collections/).

Here are a few examples:

```
$ tree ~/archive/home/lib/p60/
/Users/gareth/archive/home/lib/p60/
├── …
├── 2011-p60-cardiff-union.pdf
├── 2013-p60-boxuk.pdf
├── 2014-p60-mysociety.pdf
├── …
└── 2019-p60-mysociety.pdf

$ tree ~/archive/work/lib/sysadmin-notes/
/Users/gareth/archive/work/lib/sysadmin-notes/
├── …
├── sysadmin-notes-2015-10-29.txt
├── sysadmin-notes-2015-11-05.txt
├── …
├── sysadmin-notes-2018-08-07.md
├── …
├── sysadmin-notes-2019-08-02.md
└── sysadmin-notes-2019-08-16.md
```

I reserve `lib` for themes that I'll likely add to in the future. This could be on a regular basis, like saving my annual P60, or irregularly like the odd time I cover the daily sysadmin tasks at work. I don't keep "projects" in `lib`, as they're too prone to containing all sorts of different types of file. They just go in `doc`.

> personal files separated from work

This is pretty self explanatory – files are just sifted to `home` or `work` as appropriate, but I'll cover the odds-and-ends here.

Files that don't fit in to `lib` or `ref` directories get dumped in `doc`. The `doc` directories just contain a folder for each year:

```
$ tree -dL 1 ~/archive/home/doc/
/Users/gareth/archive/home/doc/
├── 2015
├── 2016
├── 2017
├── 2018
└── 2019
```

Depending on how full the year folder is, I'll either just dump the files directly in…

```
$ tree -L 1 ~/archive/home/doc/2018
/Users/gareth/archive/home/doc/2018
├── …
├── 2018-09-03-an-introduction-to-general-systems-thinking-graphs.numbers
├── 2018-12-25-christmas-day.txt
└── …
```

…or move the whole `YYYY-MM` folder from `~/doc`.

```
$ tree -L 1 ~/archive/work/doc/2017
/Users/gareth/archive/work/doc/2017
├── …
├── 2017-09
├── 2017-10
├── …
```

Sometimes a small theme emerges from some individual files, but its clear that they were related to a task I was doing at a specific point in time. In these cases I group them in to a dated folder.

```
$ tree -L 1 ~/archive/home/doc/2018
/Users/gareth/archive/home/doc/2018
├── …
├── 2018-02-08-4k-monitor-resolution-comparisons/
├── …
```

## Summary

Put together, I end up with a tree like this:

```
$ tree -L 3 Desktop Downloads doc archive
Desktop
└── …
Downloads
└── …
doc
├── …
├── 2019-08
├── 2019-09
├── 2019-10
├── current -> /Users/gareth/Downloads
└── previous -> /Users/gareth/doc/2019-10
archive
├── home
│   ├── doc
│   │   ├── …
│   │   ├── 2018
│   │   └── 2019
│   ├── lib
│   └── ref
└── work
    ├── doc
    │   ├── …
    │   ├── 2018
    │   └── 2019
    ├── lib
    └── ref
```

It's definitely not the _best_ form of organisation, but it works for me with minimal effort. The key to making it work well has been the automation of clearing out `~/Desktop` and `~/Downloads`, as tidying up a few files from a month or two from `~/doc` in to a simple but clear structure in `~/archive` is much less daunting than looking at hundreds, if not thousands, of files that have accumulated and wondering what to do with them all.
