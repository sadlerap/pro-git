---
title: Pro `git`
author: Andy Sadler, Red Hat
sub_title: Teaching better commit hygiene
---

Overview
--------

# What this presentation is

- A brief tour of `git`'s more advanced features
- A tutorial in wrangling commits

# My goal
Everyone will have learned at least something new.

<!-- end_slide -->

Motivation
----------

# Who's done any of the following:

- Large pull request
- All in one commit
- No comments in commit log
- PR description is almost empty

<!-- end_slide -->

These PRs are harmful
---------------------

# Reviewers must discern meaning from changes
<!-- pause -->
# Original author likely knows their approach, but the reviewer doesn't
<!-- pause -->
# This should be communicated somehow to speed up reviews
<!-- pause -->
# No record of choices made - why did the author choose their approach?
<!-- pause -->
# Terrible for history, if we have to revisit a change
<!-- pause -->
# Reverts are painful
- Need to be done manually
<!-- pause -->
# Bisects are harder to perform

<!-- end_slide -->

Something better
----------------

We can leverage git itself to make reviews easier:

<!-- pause -->
# Commits should be small and frequent

Take advantage of a branch containing multiple commits!
<!-- pause -->

- Each commit should be reviewable on its own
- Each commit should be self-contained

<!-- pause -->

# Commits should be self-descriptive

Commits should contain more than just a summary of changes.

<!-- pause -->

A good way to author commit logs:

- Describe what a commit does and why
- The how

<!-- pause -->

<!-- end_slide -->

But Andy, commit wrangling is hard!
-----------------------------------


