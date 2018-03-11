---
layout: post
title: GIT - How to use git for your project, a successful branching strategy and release management.
status: published
type: post
published: true
comments: true
category: blogs
tags: [git, branch, version control, release, release management, branching strategy]
date: 2018-03-11T16:00:00+05:30
share: true
excerpt: In this blog post you will learn a successful git branching strategy and release management.
---

I have seen many developers facing problem with version control system. I’ve worked on many projects and different git branching model.

In this blog post you will learn a successful git branching strategy and release management.

Let’s take a look on the below git branching and release flow -

![Git normal flow]({{ "/images/blog/git/normal-flow.jpg" | absolute_url }})

In the above flow - 

1. Every feature branch fork from development.
2. Feature branch merge back to development.
3. Release branch fork from development.
4. Bug fixing due to merge done in release branch. 
5. Release branch merge to master. (master branch will go to production.)
6. Add tag for release.
7. Release branch merge to development.
8. Rebase all feature branches those are not in master.


In case of hotfix on production, use below flow -

![Git hotfix flow]({{ "/images/blog/git/hotfix-flow.jpg" | absolute_url }})

In the above hotfix flow - 

1. Fork hotfix branch from master
2. Fix bug in hotfix branch
3. Merge hotfix to master
4. Add tag for hotfix
5. Merge hotfix to development
6. Rebase all feature branch those are not in master.


Commands used for this strategy.

* Fork new feature branch from development

```javascript
        $ git checkout development
        $ git checkout -b feature_branch 
    OR
        $ git checkout -b feature_branch development
```

* Merge feature branch to development

```javascript
        $ git checkout development
        $ git merge --no-ff feature_branch

    --no-ff is used for no fast forwarding, It will create a merge commit 
    rather then put all commit on development branch. This avoids losing 
    information about the historical existence of a feature branch.
```

* Adding tag

```javascript
        $ git tag -a 1.0.0 -m "Version 1.0.0 release"

    -a for add
    -m for message (optional)
    You can also use the -s or -u <key> flags to sign your tag cryptographically.
```

* Rebase feature branches -

```javascript
        $ git checkout feature_branch 
        $ git rebase <source_branch/tag>
        $ git push origin feature_branch
```

* Delete local feature branch

```javascript
        $ git branch -d feature_branch
    It throws an error if the branch is not merged to any other branch.
    If you need to delete an un-merged branch then use -D instead of -d.
```

Hope this helps