---
title: Android - Linking.open is a new activity
date: 2022-08-17
tags: ["blog", "TIL", "React Native", "Android"]
layout: layouts/post.njk
hasCodeblock: true
---

When using `Linking.open` on React Native to handle app links, Android recognizes that as a new activity, setting the [AppState](https://reactnative.dev/docs/appstate) to `background` even though the app is still open.
