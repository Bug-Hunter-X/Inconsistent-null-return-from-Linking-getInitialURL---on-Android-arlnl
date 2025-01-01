# Expo Linking.getInitialURL() Inconsistent null Return on Android

This repository demonstrates a bug in Expo's `Linking.getInitialURL()` API on Android.  The function intermittently returns `null`, even when the app is launched via a deep link. This inconsistency makes reliable deep link handling difficult.

## Bug Description

The `Linking.getInitialURL()` function, used to retrieve the initial URL that launched the app, sometimes returns `null` on Android devices. This behavior is not consistent across devices or Android versions, making it challenging to handle deep links reliably.

## Reproduction

The `LinkingBug.js` file contains code that attempts to retrieve the initial URL using `Linking.getInitialURL()`. You can observe the inconsistent `null` return by repeatedly launching the app with and without a deep link.

## Solution

The `LinkingBugSolution.js` file provides a potential workaround. It uses a combination of event listeners and a timeout to increase the chances of successfully capturing the initial URL.

## Note

This issue seems to be related to how Expo handles the initial URL retrieval and its interaction with the underlying Android system. The provided solution is a workaround and may not be perfect in all scenarios.