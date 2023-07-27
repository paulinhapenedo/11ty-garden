---
title: Filter an array using another array
date: 2022-02-02
tags: ["blog", "TIL", "javascript", "array"]
layout: layouts/post.njk
hasCodeblock: true
---

```javascript
const result = masterData.filter((ad) =>
  filterData.every((fd) => fd.userid !== md.userid)
);
```

`result` contain all `MasterData` except for things in the `FilterData`
