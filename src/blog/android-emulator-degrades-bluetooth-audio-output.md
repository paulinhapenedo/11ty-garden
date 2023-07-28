---
title: Android Emulator degrades Bluetooth audio output
date: 2022-12-16
tags: ["blog", "TIL", "Android Emulator", "Bluetooth"]
layout: layouts/post.njk
hasCodeblock: true
---

To avoid this problem, disable the microphone in the emulator by adding `hw.audioInput=no` to the `config.ini` file of the Android Virtual Device (AVD). To find an AVD's `config.ini` file, go to the AVD in the Device Manager, click its overflow menu, and select **Show on Disk**.

Reference: https://developer.android.com/studio/run/emulator-troubleshooting#emulator-degrades
