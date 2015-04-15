---
layout: post
title: GitHub-style diff in command line git
---

# {{ page.title }}

GitHub has a really nice feature that emphasises changed words in a changed line:

![Old vs New Diff word highlighting](/images/posts/github-better-word-highlighting.gif)

Here's how to get it in command line git.

![Word diff in command line git](/images/posts/github-style-word-highlight-diff-comamnd-line.png)

I've installed git on Mac OS X through [Homebrew](http://brew.sh/). If you've installed it some other way, or you're on a different system you'll need to find where [git-contrib](https://github.com/git/git/tree/master/contrib) is installed.

git-contrib includes [`diff-highlight`](https://github.com/git/git/tree/master/contrib/diff-highlight) – exactly what we're after.

Just add the following to your `~/.gitconfig`:

    [pager]
      diff = /usr/local/Library/LinkedKegs/git/share/git-core/contrib/diff-highlight/diff-highlight | less
      log  = /usr/local/Library/LinkedKegs/git/share/git-core/contrib/diff-highlight/diff-highlight | less
      show = /usr/local/Library/LinkedKegs/git/share/git-core/contrib/diff-highlight/diff-highlight | less

Note that I've used `/usr/local/Library/LinkedKegs/git` to link to the [latest version of a Homebrew formula](http://superuser.com/a/593931/123928). This will ensure `diff-highlight` is the one included with the current version of git.
