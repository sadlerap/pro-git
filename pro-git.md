---
title: Pro `git`
author: Andy Sadler, Red Hat
sub_title: Teaching better git usage
theme:
  extends: dark
  # override:
  #   footer:
  #     style: progress_bar
---

Overview
--------

<!-- alignment: center -->

# What this presentation is

- A tutorial in wrangling commits
- A brief tour of `git`'s more advanced features

<!-- end_slide -->

Scenario: Applying review to a non-HEAD commit
----------------------------------------------

You need to apply changes to a commit buried in a branch.

<!-- pause -->

Bad options:
- Add another commit to the end of the branch
<!-- pause -->
- `git checkout` + `git cherry-pick`
<!-- pause -->
- Remake your commits by hand
<!-- pause -->
- Copious application of `git commit --amend`
<!-- pause -->

<!-- end_slide -->

Scenario: Applying review to a non-HEAD commit
----------------------------------------------

# Interactive rebasing

Git has a tool for interactively managing commits:

```bash
git rebase -i origin/main # or something resembling a commit reference
```

A domain-specific language for rewriting a branch's history

<!-- pause -->

Some commands:
- `pick <commit>`: use commit
- `reword <commit>`: use commit, but edit the commit message
- `edit <commit>`: use commit, but stop for amending
- `squash <commit>`: use commit, but meld into previous commit
- `fixup <commit>`: squash's a commit into the previous commit.  Uses the
previous commit's message

<!-- end_slide -->

Scenario: Applying review to a non-HEAD commit
----------------------------------------------

Git can configure a commit to be automatically squashed into another commit (called a *fixup*):

```bash
git commit --fixup=<commit> # make a commit
git rebase --autosquash <commit> # apply squashes since <commit>
```

Useful if your change applies cleanly to a previous commit.  Less useful for
more invasive changes.

Enable by default with:
```bash
git config --global rebase.autoSquash true
```

<!-- end_slide -->

Scenario: Fixing a broken branch
--------------------------------

You've just rebased a branch, and you lost all your commits.

<!-- end_slide -->

Scenario: Fixing a broken branch
--------------------------------

Git contains a history of every modification you've made to a branch, called
the *reflog*:

```bash
git reflog
```

<!-- end_slide -->

Scenario: Fixing a broken branch
--------------------------------

Example usage:

```bash +exec
git -C ~/repos/mpc reflog main
```

<!-- end_slide -->

Scenario: Splitting commits in an unclean tree
----------------------------------------------

You want to split your commits, but your changes should ideally be split into
multiple commits.

Bad options:
- Remake your changes and stage accordingly
<!-- pause -->
- Abuse `git stash`... somehow?
<!-- pause -->
- Put everything into one commit?

<!-- end_slide -->

Scenario: Splitting commits in an unclean tree
----------------------------------------------

You can stage changes interactively:

```bash
git add -i # stage changes interactively
git add -p <file> # stage changes through a prompt
```

<!-- end_slide -->

Scenario: Working on multiple features concurrently
---------------------------------------------------

You've been assigned multiple tasks on the same repository this sprint, and you
want to work on them concurrently.

Bad options:
- `git checkout`/`git switch` whenever you change contexts
<!-- pause -->
- Multiple clones of the same repository locally
<!-- pause -->
- Work on things in serial (sorry management)

<!-- end_slide -->

Scenario: Working on multiple features concurrently
---------------------------------------------------

Git supports checking out the same clone of a repository in multiple locations
(these directories are called *worktrees*):

```bash
git worktree add # make a new directory with a clone
git worktree list # what worktree's have you made?
git worktree remove # make a new directory with a clone
```

Limitation: two worktrees cannot have the same commit checked out at the same time!

<!-- end_slide -->

Further reading
---------------

Julia Evan's blog posts on git:
- https://jvns.ca/blog/2023/11/23/branches-intuition-reality/

The git book:
- https://git-scm.com/book/en/v2

<!-- end_slide -->

Materials
---------

Materials from this presentation can be obtained here:

```bash +exec_replace +no_background
echo https://github.com/sadlerap/pro-git | qrencode -t UTF8i -m 2 | lolcat -f
```
```
https://github.com/sadlerap/pro-git
```
