---
title: How to stop the emulator process on MacOs
date: 2022-05-27
tags: ["blog", "TIL", "Android Emulator", "macos"]
layout: layouts/post.njk
hasCodeblock: true
---

As seen here https://stackoverflow.com/questions/20155376/android-stop-emulator-from-command-line

```bash
ps -ax | grep emulator

# returns something like

6617 ??         9:05.54 /Users/nav/Library/Android/sdk/emulator/qemu/darwin-x86_64/qemu-system-x86_64 -netdelay none -netspeed full -avd Nexus_One_API_29
 6619 ??         0:06.10 /Users/nav/Library/Android/sdk/emulator/emulator64-crash-service -pipe com.google.AndroidEmulator.CrashService.6617 -ppid 6617 -data-dir /tmp/android-nav/
 6658 ??         0:07.93 /Users/nav/Library/Android/sdk/emulator/lib64/qt/libexec/QtWebEngineProcess --type=renderer --disable-accelerated-video-decode --disable-gpu-memory-buffer-video-frames --disable-pepper-3d-image-chromium --enable-threaded-compositing --file-url-path-alias=/gen=/Users/nav/Library/Android/sdk/emulator/lib64/qt/libexec/gen --enable-features=AllowContentInitiatedDataUrlNavigations --disable-features=MacV2Sandbox,MojoVideoCapture,SurfaceSynchronization,UseVideoCaptureApiForDevToolsSnapshots --disable-gpu-compositing --service-pipe-token=15570406721898250245 --lang=en-US --webengine-schemes=qrc:sLV --num-raster-threads=4 --enable-main-frame-before-activation --service-request-channel-token=15570406721898250245 --renderer-client-id=2
 6659 ??         0:01.11 /Users/nav/Library/Android/sdk/emulator/lib64/qt/libexec/QtWebEngineProcess --type=renderer --disable-accelerated-video-decode --disable-gpu-memory-buffer-video-frames --disable-pepper-3d-image-chromium --enable-threaded-compositing --file-url-path-alias=/gen=/Users/nav/Library/Android/sdk/emulator/lib64/qt/libexec/gen --enable-features=AllowContentInitiatedDataUrlNavigations --disable-features=MacV2Sandbox,MojoVideoCapture,SurfaceSynchronization,UseVideoCaptureApiForDevToolsSnapshots --disable-gpu-compositing --service-pipe-token=--lang=en-US --webengine-schemes=qrc:sLV --num-raster-threads=4 --enable-main-frame-before-activation --service-request-channel-token=  --renderer-client-id=3
10030 ttys000    0:00.00 grep emulator
```

running `kill PID` should suffice. (PID is the first number).
