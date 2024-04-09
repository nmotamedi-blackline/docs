---
title: Branching Model
type: docs
prev: /
next: docs/folder/
---

## A brief introduction

## Tags vs Branches

A branch is a reference to the latest commit in a series of commits. This means when using a branch, we are not referring to a very specific point in repository's history. This is usually used to work on a new feature or bug fix (as we prefer to start from the most recent work).
A tag on the other hand is a reference to a specific point in the repository's history, like a snapshot of the repository taken at the moment the tag was created. This is usually used to mark a release as tags unlike branches remain static and do not change.

Considering these differences, we're going to use branches and tags for different purposes, mainly:

1. To work on new features or bug fixes, we'll use branches.
2. To mark a release and deploy it to different environments, we'll use tags.

## Overview Branches and their purpose

Here is a quick overview of main branches in the repository. We will go into more detail about each of them in the following sections. Also worth noting these are not the only branches that can exist in the repository, but the main ones that we will be using.

### master

This branch is where we tag the latest release. It is the most stable branch and should always be in a deployable state. When we want to release a new version of the software, we will create a new tag from this branch and deploy it to the desired environment.
Unlike feature branches, hotfixes should be based on the latest tag in this branch.
### next

This branch is where we integrate all the new features we work on. Later we will merge this branch into master when we are ready to release a new version. We will create tags in this branch as well, but they will be release candidates, not final releases.
Our goal is to keep this branch as close to master as possible.

## Feature branches

These are temporary branches that we create when working on a new feature. We will create them from the `next` branch and once the work is done, we will merge them back into the `next` branch and eventually will delete them.

### When starting working on a new feature

TODO: This section is just a scrathpad for while writing the main article.

* Next version number (chronologically) should not be smaller than the currently deployed version number.
  * This is to avoid confusion when deploying a new version.
  * Bugs can be fixed in the current version and deployed without affecting the next version.
  * Bug fixes should always be based on latest released version.
