# PerformanceElementTiming.loadTime

The `loadTime` read-only property of the [`PerformanceElementTiming`](../performanceelementtiming) interface always returns 0 for text. For images it returns the time which is the latest between the time the image resource is loaded and the time it is attached to the element.

## Syntax

    var loadTime = PerformanceElementTiming.loadTime;

### Value

A [`DOMHighResTimeStamp`](../domhighrestimestamp) with the loadTime of the element.

## Examples

In this example calling `entry.loadTime` returns the loadTime of the image element.

    <img src="image.jpg" alt="a nice image" elementtiming="big-image" id="myImage">

    const observer = new PerformanceObserver((list) => {
      let entries = list.getEntries().forEach(function (entry) {
        if (entry.identifier === "big-image") {
          console.log(entry.loadTime);
        }
      });
    });
    observer.observe({ entryTypes: ["element"] });

This example uses the [`PerformanceObserver`](../performanceobserver) interface to create a list of performance measurement events. In our case we observe the [`PerformanceEntry.entrytype`](../performanceentry/entrytype) `element` in order to use the `PerformanceElementTiming` interface.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/element-timing/#dom-performanceelementtiming-loadtime">Element Timing<br />
<span class="small">The definition of 'PerformanceElementTiming.loadTime' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`loadTime`

77

79

No

No

64

No

77

77

No

55

No

12.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceElementTiming/loadTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceElementTiming/loadTime</a>
