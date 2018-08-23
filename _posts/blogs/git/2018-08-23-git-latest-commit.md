---
layout: post
title: GIT - How to find the latest git commit from all branches.
status: published
type: post
published: true
comments: true
category: blogs
tags: [git, branch, version control, bash, latest, commit, all]
date: 2018-08-23T00:00:00+05:30
share: true
excerpt: In this blog post you will learn, how to find the latest git commit from all branches.
---

To find the latest ggit coomit from all branches, you need to understand with some set of commands.

Command 1: List all remote branches.

```
 
git branch -r

```
Note: If you wants to find it from your local branches then don't use '-r', as '-r' is used for remote branches. You can use '--remote' instead of '-r' as well.


Command 2: Select all branches except HEAD via using grep command.

```

git branch -r | grep -v HEAD

```
Note: We are using '-v' for invert match, we can also use '--invert-match' instead of '-v'.


Command 3: Show commit in format with date.

```

git show --format="%ci %cr" branch_name

```
Note: '%ci' for committer date in ISO 8601 format
      '%cr' for relative committer date


Command 4: sort the commits.

```

sort -r

```
Note: '-r' used for reverse, we can use '--reverse' insted of '-r'


Here is the complete one liner script to achieve it -

```

for branch in `git branch -r | grep -v HEAD`;do echo -e `git show --format="%ci %cr" $branch | head -n 1` \\t$branch; done | sort -r | head -1

```

Goto your repository and run above script to get latest commit.

Thanks Kirti for asking such a good question.

Hope this helps