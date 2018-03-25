---
layout: post
title: GIT - How to get git bash git completion in MacOS.
status: published
type: post
published: true
comments: true
category: blogs
tags: [git, branch, version control, bash, auto, auto completion, macOS]
date: 2018-03-26T00:00:00+05:30
share: true
excerpt: In this blog post you will learn, how to get git bash auto-completion in MacOS.
---

Git Autocomplition for macOS

There are two ways for it.

By far the easiest way to install git-completion is below -

```

curl https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.bash -o ~/.git-completion.bash && echo "source ~/.git-completion.bash" >> ~/.bash_profile && source ~/.bash_profile

```

You just need to copy above line and execute it in terminal.


Another way,

Install both Git and git-completion is via Homebrew, so you should pick that one.

```
 
brew install git && brew install bash-completion

```

Note: If you already have git installed then just execute below command -

```
 
brew install bash-completion

```

and then add bash-completion to your ~/.bash_profile:

```

if [ -f $(brew --prefix)/etc/bash_completion ]; then
  . $(brew --prefix)/etc/bash_completion
fi

```

After all either execute .bash_profile or just open a new terminal.

Congrats your git bash autocompletion is now working.

Hope this helps