# PerformanceElementTiming.naturalHeight

The `naturalHeight` read-only property of the [`PerformanceElementTiming`](../performanceelementtiming) interface returns the intrinsic height of the image element.

## Syntax

    var height = PerformanceElementTiming.naturalHeight;

### Value

An unsigned 32-bit integer (unsigned long) which is the intrinsic height of the image if this is applied to an image, 0 for text.

## Examples

In this example the image file has a width of 1000px and a height of 750px. Calling `entry.naturalHeight` returns `750`, that being the intrinsic height in pixels.

    <img src="image.jpg" alt="a nice image" elementtiming="big-image" id="myImage">

    const observer = new PerformanceObserver((list) => {
      let entries = list.getEntries().forEach(function (entry) {
        if (entry.identifier === "big-image") {
          console.log(entry.naturalHeight);
        }
      });
    });
    observer.observe({ entryTypes: ["element"] });

This example uses the [`PerformanceObserver`](../performanceobserver) interface to create a list of performance measurement events. In our case we observe the [`PerformanceEntry.entrytype`](../performanceentry/entrytype) `element` in order to use the `PerformanceElementTiming` interface.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/element-timing/#dom-performanceelementtiming-naturalheight">Element Timing<br />
<span class="small">The definition of 'PerformanceElementTiming.naturalHeight' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`naturalHeight`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceElementTiming/naturalHeight" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceElementTiming/naturalHeight</a>
