---
title: Troubleshooting
sidebar_position: 4
---

## Why are my folders and files not visible in iCloud drive folder?

1. Make sure your `NSUbiquitousContainers` config in `Info.plist` is correct
2. Make sure your path passed to API includes `'Documents'`, for example `'/path-to-icloud-container/Documents/myCustomContent'` but not `'/path-to-icloud-container/myCustomContent'`
3. if the above are correct, try to bump your build version in XCode/Info.plist and rebuild

## What is `.xxx.icloud` file?
When reading iCloud dir, you would find files named like `.xxx.icloud`, this format means the file has not downloaded to your local device, it's currently stored on iCloud drive. You can call `download` to download it, after it is downloaded, re-call `readDir` and you will find `.xxx.icloud` has become `xxx`, then you can use a package such as `react-native-fs` to copy it from the iCloud container to your app's documents folder.
