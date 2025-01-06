# React Native Dimensions API Bug

This repository demonstrates a bug where the `Dimensions` API in React Native returns incorrect dimensions (0, 0) inconsistently, especially during app launch or screen rotation.  This leads to layout problems and potential crashes.

## Bug Description

The `Dimensions.get('window')` method sometimes returns inaccurate width and height values, including 0, 0. This behavior is non-deterministic.  The bug is more likely to happen on slower devices or when there are other performance bottlenecks.

## Solution

The problem is addressed by using the `onLayout` event and the `useEffect` hook to ensure that the dimensions are accurately retrieved after the component has rendered and the layout is finalized. This avoids relying on potentially incomplete or inaccurate data provided immediately after launch.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` or `yarn install`.
3. Run the app on a physical device or emulator.
4. Observe the console logs to see if 0,0 is returned initially.
5. Rotate the screen. The issue might be more obvious after screen rotation.
