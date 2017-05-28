---
title: Git
published: true
date: '28-05-2017 11:24'
publish_date: '28-05-2017 11:24'
taxonomy:
    category:
        - docs
menu: Git
slug: git
---

Merge all Commits

```
git checkout --orphan new-master master
git commit -m "Enter commit message for your new initial commit"

# Overwrite the old master branch reference with the new one
git branch -M new-master master
```