# Element Timing API

The **Element Timing API** provides features for monitoring the loading performance of large image elements and text nodes as they appear on screen.

## Concepts and Usage

The aim of the Element Timing API is to give web developers or analytics tools the ability to measure rendering timestamps of critical elements on a page.

The API supports timing information on [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) elements, [`<image>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/image) elements inside an [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/svg), poster images of [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) elements, elements which have a [`background-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-image), and groups of text nodes, such as a [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p).

The author flags an element for observation by adding the [`elementtiming`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/for) attribute on the element.

## Interfaces

[`PerformanceElementTiming`](performanceelementtiming)  
Reports timing information about one associated element.

## Examples

In this example we have two elements which are being observed. We use the [`PerformanceObserver`](performanceobserver) interface to create a list of performance measurement events, in our case observing the [`PerformanceEntry.entrytype`](performanceentry/entrytype) `element` in order to use the `PerformanceElementTiming` interface from the Element Timing API.

Two entries will be output to the console, the first containing details of the image, the second with details of the text node.

    <img src="image.jpg" elementtiming="big-image">
    <p elementtiming="text" id="text-id">text here</p>

    const observer = new PerformanceObserver((list) => {
      let entries = list.getEntries().forEach(function (entry) {
          console.log(entry);
      });
    });
    observer.observe({ entryTypes: ["element"] });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/element-timing/">Element Timing</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Element_timing_API`

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

BCD tables only load in the browser

## See also

- [`PerformanceFrameTiming`](performanceframetiming)
- [`PerformanceNavigationTiming`](performancenavigationtiming)
- [`PerformanceResourceTiming`](performanceresourcetiming)
- [`PerformanceMark`](performancemark)
- [`PerformanceMeasure`](performancemeasure)
- [`PerformancePaintTiming`](performancepainttiming)
- [`PerformanceLongTaskTiming`](performancelongtasktiming)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element_timing_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element_timing_API</a>
