---
title: Recover a dropped stash commit
date: 2022-08-22
tags: ["blog", "TIL", "git"]
layout: layouts/post.njk
hasCodeblock: true
---

```bash
git fsck --unreachable | grep commit | cut -c 20- | xargs git show | grep -B 6 -A 2 <name of the stash>

## brings results like
## commit COMMIT_HASH
## Merge: MERGE_HASH (when the drop happened)
## Author
## Date

git stash apply COMMIT_HASH
```
