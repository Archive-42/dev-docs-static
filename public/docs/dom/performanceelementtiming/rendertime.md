# PerformanceElementTiming.renderTime

The `renderTime` read-only property of the [`PerformanceElementTiming`](../performanceelementtiming) interface returns the render time of the associated element.

## Syntax

    var renderTime = PerformanceElementTiming.renderTime;

### Value

A [`DOMHighResTimeStamp`](../domhighrestimestamp) with the render time of the element.

For images this will be the **image rendering timestamp**. This is defined as the next paint that occurs after the image becomes fully loaded. If the timing allow check fails (as defined by the [Timing-allow-origin](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Timing-Allow-Origin) header) this will return 0.

For text nodes this will be the **text rendering timestamp**. This is defined as when the element becomes text painted.

## Examples

In this example calling `entry.renderTime` returns the render time of the image element.

    <img src="image.jpg" alt="a nice image" elementtiming="big-image" id="myImage">

    const observer = new PerformanceObserver((list) => {
      let entries = list.getEntries().forEach(function (entry) {
        if (entry.identifier === "big-image") {
          console.log(entry.renderTime);
        }
      });
    });
    observer.observe({ entryTypes: ["element"] });

This example uses the [`PerformanceObserver`](../performanceobserver) interface to create a list of performance measurement events. In our case we observe the [`PerformanceEntry.entrytype`](../performanceentry/entrytype) `element` in order to use the `PerformanceElementTiming` interface.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/element-timing/#dom-performanceelementtiming-rendertime">Element Timing<br />
<span class="small">The definition of 'PerformanceElementTiming.renderTime' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`renderTime`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceElementTiming/renderTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceElementTiming/renderTime</a>
