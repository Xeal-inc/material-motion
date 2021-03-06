---
layout: page
title: y
status:
  date: February 21, 2016
  is: Stable
interfacelevel: L2
implementationlevel: L3
library: material-motion
depends_on:
  - /starmap/specifications/operators/foundation/$._map
availability:
  - platform:
    name: Android
    url: https://github.com/material-motion/material-motion-android/blob/develop/library/src/main/java/com/google/android/material/motion/operators/Y.java
  - platform:
    name: iOS (Swift)
    url: https://github.com/material-motion/material-motion-swift/blob/develop/src/operators/y.swift
    tests_url: https://github.com/material-motion/material-motion-swift/blob/develop/tests/unit/operator/yTests.swift
related_to:
  - /starmap/specifications/operators/x
interaction:
  inputs:
    - input:
      name: upstream
      type: Point
  outputs:
    - output:
      name: downstream
      type: number
---

# y specification

This is the engineering specification for the `MotionObservable` operator: `y`.

## Overview

`y` extracts the y value from a Point stream.

Example usage:

```swift
stream.y()

upstream        |  downstream
{x: 20, y: 25}  |  25
{x: 40, y: 10}  |  10
{x: 70, y: 30}  |  30
```

## MVP

### Expose a y operator API

Use `_map` to implement the operator. Return the x value. Exposed on streams of type Point.

```swift
class MotionObservable<Point> {

  public func y() -> MotionObservable<Float> { return _map { return $0.y } }
```
