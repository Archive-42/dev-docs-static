# PerformanceElementTiming.intersectionRect

The `intersectionRect` read-only property of the [`PerformanceElementTiming`](../performanceelementtiming) interface returns the rectangle of the element within the viewport.

## Syntax

    var rect = PerformanceElementTiming.intersectionRect;

### Value

A [`DOMRectReadOnly`](../domrectreadonly) which is the rectangle of the element within the viewport.

For display images this is the display rectangle of the image within the viewport. For text this is the display rectangle of the node in the viewport. This being the smallest rectangle that contains the union of all text nodes that belong to the element.

## Examples

In this example calling `entry.intersectionRect` returns a [`DOMRectReadOnly`](../domrectreadonly) object with the display rectangle of the image.

    <img src="image.jpg" alt="a nice image" elementtiming="big-image" id="myImage">

    const observer = new PerformanceObserver((list) => {
      let entries = list.getEntries().forEach(function (entry) {
        if (entry.identifier === "big-image") {
          console.log(entry.intersectionRect);
        }
      });
    });
    observer.observe({ entryTypes: ["element"] });

This example uses the [`PerformanceObserver`](../performanceobserver) interface to create a list of performance measurement events. In our case we observe the [`PerformanceEntry.entrytype`](../performanceentry/entrytype) `element` in order to use the `PerformanceElementTiming` interface.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/element-timing/#dom-performanceelementtiming-intersectionrect">Element Timing<br />
<span class="small">The definition of 'PerformanceElementTiming.intersectionRect' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`intersectionRect`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceElementTiming/intersectionRect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceElementTiming/intersectionRect</a>
