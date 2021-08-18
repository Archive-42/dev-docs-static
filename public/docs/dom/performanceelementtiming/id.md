PerformanceElementTiming.id
===========================

The `id` read-only property of the [`PerformanceElementTiming`](../performanceelementtiming) interface returns the [`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-id) of the associated element.

Syntax
------

    var id = PerformanceElementTiming.id;

### Value

A [`DOMString`](../domstring).

Examples
--------

In this example calling `entry.id` will log to the console `myImage`, this being the [`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-id) of the image element.

    <img src="image.jpg" alt="a nice image" elementtiming="big-image" id="myImage">

    const observer = new PerformanceObserver((list) => {
      let entries = list.getEntries().forEach(function (entry) {
        if (entry.identifier === "big-image") {
          console.log(entry.id);
        }
      });
    });
    observer.observe({ entryTypes: ["element"] });

This example uses the [`PerformanceObserver`](../performanceobserver) interface to create a list of performance measurement events. In our case we observe the [`PerformanceEntry.entrytype`](../performanceentry/entrytype) `element` in order to use the `PerformanceElementTiming` interface.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/element-timing/#dom-performanceelementtiming-id">Element Timing<br />
<span class="small">The definition of 'PerformanceElementTiming.id' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`id`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceElementTiming/id" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceElementTiming/id</a>
