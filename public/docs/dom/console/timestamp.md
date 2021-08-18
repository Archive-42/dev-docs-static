# Console.timeStamp()

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Adds a single marker to the browser's [Performance](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference) or [Waterfall](https://developer.mozilla.org/en-US/docs/Tools/Performance/Waterfall) tool. This lets you correlate a point in your code with the other events recorded in the timeline, such as layout and paint events.

You can optionally supply an argument to label the timestamp, and this label will then be shown alongside the marker.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    console.timeStamp(label);

## Parameters

`label`  
Label for the timestamp. Optional.

## Browser compatibility

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`timeStamp`

14

12

39

11

15

6

≤37

18

39

14

6

1.0

## See also

- [`Console.time()`](time)
- [`Console.timeEnd()`](timeend)
- [Adding timestamps to the Waterfall](https://developer.mozilla.org/en-US/docs/Tools/Performance/Waterfall#timestamp_markers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Console/timeStamp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Console/timeStamp</a>
