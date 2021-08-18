# PerformanceElementTiming.naturalWidth

The `naturalWidth` read-only property of the [`PerformanceElementTiming`](../performanceelementtiming) interface returns the intrinsic width of the image element.

## Syntax

    var width = PerformanceElementTiming.naturalWidth;

### Value

An unsigned 32-bit integer (unsigned long) which is the intrinsic width of the image if this is applied to an image, 0 for text.

## Examples

In this example the image file has a width of 1000px and a height of 750px. Calling `entry.naturalWidth` returns `1000`, that being the intrinsic width in pixels.

    <img src="image.jpg" alt="a nice image" elementtiming="big-image" id="myImage">

    const observer = new PerformanceObserver((list) => {
      let entries = list.getEntries().forEach(function (entry) {
        if (entry.identifier === "big-image") {
          console.log(entry.naturalWidth);
        }
      });
    });
    observer.observe({ entryTypes: ["element"] });

This example uses the [`PerformanceObserver`](../performanceobserver) interface to create a list of performance measurement events. In our case we observe the [`PerformanceEntry.entrytype`](../performanceentry/entrytype) `element` in order to use the `PerformanceElementTiming` interface.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/element-timing/#dom-performanceelementtiming-naturalwidth">Element Timing<br />
<span class="small">The definition of 'PerformanceElementTiming.naturalWidth' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`naturalWidth`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceElementTiming/naturalWidth" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceElementTiming/naturalWidth</a>
