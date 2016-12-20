---
layout: page
title: ScrollSource
status:
  date: December 13, 2016
  is: Draft
knowledgelevel: L2
library: springs
depends_on:
  - /starmap/specifications/streams/MotionObservable/
---

# ScrollSource specification

This is the engineering specification for the `ScrollSource` type.

## Overview

A `ScrollSource` is a function that accepts a scrollable element and returns a MotionObservable
capable of emitting scroll offset values.

Example usage:

```swift
scrollSource(scrollableElement).subscribe(...)
```

```java
ScrollSource.from(scrollableElement).subscribe(...)
```

## MVP

### Expose generic ScrollSource API

`ScrollSource` is a function signature. It accepts a scrollable element and returns a
MotionObservable that emits Point values.

```swift
public typealias ScrollSource = (ScrollableElement) -> MotionObservable<Point>
```