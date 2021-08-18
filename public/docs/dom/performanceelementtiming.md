# PerformanceElementTiming

The `PerformanceElementTiming` interface of the [Element Timing API](element_timing_api) reports timing information on a specific element identified by the page author. For example it could report timing information about the main image in an article.

## Properties

[`PerformanceElementTiming.element`](performanceelementtiming/element)<span class="badge inline readonly">Read only </span>  
An [`Element`](element) representing the element we are returning information about.

[`PerformanceElementTiming.id`](performanceelementtiming/id)<span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) which is the [`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-id) of the element.

[`PerformanceElementTiming.identifier`](performanceelementtiming/identifier)<span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) which is the value of the [`elementtiming`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/for) attribute on the element.

[`PerformanceElementTiming.intersectionRect`](performanceelementtiming/intersectionrect)<span class="badge inline readonly">Read only </span>  
A [`DOMRectReadOnly`](domrectreadonly) which is the rectangle of the element within the viewport.

[`PerformanceElementTiming.loadTime`](performanceelementtiming/loadtime)<span class="badge inline readonly">Read only </span>  
A [`DOMHighResTimeStamp`](domhighrestimestamp) with the loadTime of the element.

[`PerformanceElementTiming.naturalHeight`](performanceelementtiming/naturalheight)<span class="badge inline readonly">Read only </span>  
An unsigned 32-bit integer (unsigned long) which is the intrinsic height of the image if this is applied to an image, 0 for text.

[`PerformanceElementTiming.naturalWidth`](performanceelementtiming/naturalwidth)<span class="badge inline readonly">Read only </span>  
An unsigned 32-bit integer (unsigned long) which is the intrinsic width of the image if this is applied to an image, 0 for text.

[`PerformanceElementTiming.renderTime`](performanceelementtiming/rendertime)<span class="badge inline readonly">Read only </span>  
A [`DOMHighResTimeStamp`](domhighrestimestamp) with the renderTime of the element.

[`PerformanceElementTiming.url`](performanceelementtiming/url)<span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) which is the initial URL of the resources request for images, 0 for text.

## Methods

[`PerformanceElementTiming.toJSON()`](performanceelementtiming/tojson)  
Generates a JSON description of the object.

## Examples

In this example we have two elements which are being observed. We use the [`PerformanceObserver`](performanceobserver) interface to create a list of performance measurement events. In our case observing the [`PerformanceEntry.entrytype`](performanceentry/entrytype) `element` in order to use the `PerformanceElementTiming` interface.

Two entries will be output to the console. The first containing details of the image, the second with details of the text node.

    <img src="image.jpg" elementtiming="big-image">
    <p elementtiming="text" id="text-id">text here</p>

    const observer = new PerformanceObserver((list) => {
      let entries = list.getEntries().forEach(function (entry) {
          console.log(entry);
      });
    });
    observer.observe({ entryTypes: ["element"] });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/element-timing/#sec-performance-element-timing">Element Timing<br />
<span class="small">The definition of 'PerformanceElementTiming' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PerformanceElementTiming`

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

`element`

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

`identifier`

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

`url`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceElementTiming" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceElementTiming</a>
