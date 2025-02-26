---
title: MediaRecorder.pause()
slug: Web/API/MediaRecorder/pause
---

{{APIRef("MediaStream Recording")}}

The **`Media.pause()`** method (part of the [MediaRecorder API](/zh-CN/docs/Web/API/MediaRecorder_API)) is used to pause recording of media streams.

When a `MediaRecorder` object’s `pause()`method is called, the browser queues a task that runs the below steps:

1. If {{domxref("MediaRecorder.state")}} is "inactive", raise a DOM `InvalidState` error and terminate these steps. If not, continue to the next step.
2. Set {{domxref("MediaRecorder.state")}} to "paused".
3. Stop gathering data into the current {{domxref("Blob")}}, but keep it available so that recording can be resumed later on.
4. Raise a {{event("pause")}} event.

## Syntax

```plain
MediaRecorder.pause()
```

### Return value

`undefined`.

### Exceptions

- `InvalidStateError`
  - : The `MediaRecorder` is currently `"inactive"`; you can't pause recording if it's not active. If you call `pause()` while already paused, it silently does nothing.

## Example

```js
...

 pause.onclick = function() {
     mediaRecorder.pause();
     console.log("recording paused");
 }

...
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [Using the MediaRecorder API](/zh-CN/docs/Web/API/MediaRecorder_API/Using_the_MediaRecorder_API)
- [Web Dictaphone](http://mdn.github.io/web-dictaphone/): MediaRecorder + getUserMedia + Web Audio API visualization demo, by [Chris Mills](https://twitter.com/chrisdavidmills) ([source on Github](https://github.com/mdn/web-dictaphone/).)
- [simpl.info MediaStream Recording demo](http://simpl.info/mediarecorder/), by [Sam Dutton](https://twitter.com/sw12).
- {{domxref("Navigator.getUserMedia")}}
