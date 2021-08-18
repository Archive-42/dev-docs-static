PerformanceElementTiming.toJSON()
=================================

The `toJSON()` method of the [`PerformanceElementTiming`](../performanceelementtiming) interface is a standard serializer. It returns a JSON representation of the object's properties.

Syntax
------

    var json = PerformanceElementTiming.toJSON();

### Return value

json  
A JSON object that is the serialization of the `PerformanceElementTiming` object.

Examples
--------

In this example calling `entry.toJSON()` returns a JSON representation of the `PerformanceElementTiming` object, with the information about the image element.

    <img src="image.jpg" alt="a nice image" elementtiming="big-image" id="myImage">

    const observer = new PerformanceObserver((list) => {
      let entries = list.getEntries().forEach(function (entry) {
        if (entry.identifier === "big-image") {
          console.log(entry.toJSON());
        }
      });
    });
    observer.observe({ entryTypes: ["element"] });

This example uses the [`PerformanceObserver`](../performanceobserver) interface to create a list of performance measurement events. In our case we observe the [`PerformanceEntry.entrytype`](../performanceentry/entrytype) `element` in order to use the `PerformanceElementTiming` interface.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/element-timing/#dom-performanceelementtiming-tojson">Element Timing<br />
<span class="small">The definition of 'PerformanceElementTiming.toJson()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`toJSON`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceElementTiming/toJSON" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceElementTiming/toJSON</a>
