---
layout: post
title: Set Git Branch In Your Bash Prompt
meta: How to set the current git branch in your bash prompt
---

# {{ page.title }}

I use [git](http://git-scm.com) for my source code management and branch regularly.

It's good to know which branch your on when your performing command line tasks. You can run `git branch`, but that gets tedious.

You can add a function to your `.profile` (or `.bash_profile` etc) to get a prompt that looks like:

```sh
gareth:garethrees.github.com (master)$
```

This outputs the current user (denoted by `\u`) followed by the current directory (`\W`) and finally the git branch inside parentheses.

When you're not in a git repository the prompt omits the parentheses and git branch.

## Show me the code

```sh
parse_git_branch() {
 git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}

export PS1="\u:\W \$(parse_git_branch)$ "
```