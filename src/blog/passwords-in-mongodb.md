---
title: Passwords in MongoDB
date: 2021-11-02
tags: ["blog", "TIL", "mongodb"]
layout: layouts/post.njk
---

If you have a strong password, the one with special characters, and you need to pass it into a connection string URI, you have to escape the special characters using **percent encoding** as seen here: [Special Characters in Connection String Password](https://docs.atlas.mongodb.com/troubleshoot-connection/#special-characters-in-connection-string-password).
