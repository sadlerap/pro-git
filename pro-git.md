---
title: Pro `git`
author: Andy Sadler, Red Hat
sub_title: Teaching better commit hygiene
theme:
  extends: dark
  override:
    footer:
      style: progress_bar
---

Overview
--------

# What this presentation is

- A brief tour of `git`'s more advanced features
- A tutorial in wrangling commits

# My goal
Everyone will have learned at least something new.

<!-- end_slide -->

Git's data model
----------------

<!-- column_layout: [2, 3] -->

<!-- pause -->

<!-- column: 0 -->

# Commits

A commit is a node in a directed acyclic graph.

<!-- pause -->

They contain some important information:

- Author and Date
- A commit message
- A tree (all the files you have in that commit)
  - Commits don't contain diffs!

<!-- pause -->

Commits have important properties:

- Immutable
- Uniquely identified by hash (barring attacks on SHA-1)

<!-- column: 1 -->

<!-- pause -->

```commit +no_background {1|2-3|4-19|21-23}
tree 78db4929efd8cc3bad6c57128912bf58fa2fb479
author Andy Sadler <ansadler@redhat.com> 1751918585 -0500
committer Andy Sadler <ansadler@redhat.com> 1751918585 -0500
gpgsig -----BEGIN PGP SIGNATURE-----
 
 iQIzBAABCgAdFiEE/gSIuZZ6oleJBl8UelM1fNWBc90FAmhsJ/sACgkQelM1fNWB
 c93m1Q//TUMkPLk6/C5KuLmeizL64MWYzvl3/qYgkeve9aJh0owVQbbhiS8yngid
 9TX7idP1cAOYELPLGSx2Yq5vyMTHp3kufrrO4XseXP1oT05ZD1+W2U5gzPyRW6NI
 0cS2BUy0bFbToBFZgIIq3i2zUE6v6m/P5/QiHqTYhkkwqtm+D0PC+sNhW9Ov1dZm
 bj97+qkoAAsKMLpOuS+5u3Y5szNy4+XXVOF49u663XFmGD7N3vtf+vPL68Db0kFJ
 JLy/9bmkLeAL6IXldGKFvP/Hvlj9azPgUa5sjV4f1jtctFfHQmOT3qtULSmPfegb
 IpPumxUeHkT+e86MJZwEYT3FV/S5j3Id6CizZEMdWwANpNjreDrA70fDc6wGmUND
 f0x6P8zUFpUAJS8yOfVaxrtr/NsIJ9Vl6kH7Who4AbDzaibdC38QN/rRqOIVm/fE
 6qcG/ur1zeX18jHOEOlu3c0yIKxZ1rF3BjA6hsKwvfgAB8+AphtmkymHQnUc2H3G
 AYfzCofCEIbPLRFbNlVBzU7burAP0J94j80RlibpPLvibnwEIKR1QoAnvuw4dQ6G
 sY+Ym1z6Rc9aUII0hklW2j/kR6okhEhRJ611cuYUi5Wp0+URCQ1sRGITq4xdzG5E
 Flo/8Jc8J/BxBhvWZ6Ola0N61UxEvgXxsP9keR9kcR5r8cBVRnQ=
 =l0xS
 -----END PGP SIGNATURE-----

initial commit

Signed-off-by: Andy Sadler <ansadler@redhat.com>
```

<!-- end_slide -->

Git's data model
----------------

<!-- column_layout: [2, 4] -->

<!-- column: 0 -->

# Branches

Branches are a pointer to a commit.

They also track the history of that pointer, keeping a record of every commit
that the branch has referenced.

<!-- column: 1 -->

```bash +exec +no_background
git reflog HEAD | tail
```

<!-- end_slide -->

# Further reading

- https://jvns.ca/blog/2023/11/23/branches-intuition-reality/

<!-- end_slide -->

# Materials

Materials from this presentation can be obtained here:

```bash +exec_replace +no_background
echo https://github.com/sadlerap/pro-git | qrencode -t UTF8i -m 2 | lolcat -f
```
