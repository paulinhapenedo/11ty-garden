---
title: Create a fake test file on MacOS
date: 2022-04-08
tags: ["blog", "TIL", "bash"]
layout: layouts/post.njk
hasCodeblock: true
---

If you want to test your upload limits, you can create a file on MacOS by typing on the command line:

```bash
## mkfile ${size} ${name}.${extension}

mkfile 10m myTestFile.pdf
```
