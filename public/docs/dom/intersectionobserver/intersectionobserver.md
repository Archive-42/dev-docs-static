# IntersectionObserver.IntersectionObserver()

The `IntersectionObserver()` constructor creates and returns a new [`IntersectionObserver`](../intersectionobserver) object. The `rootMargin`, if specified, is checked to ensure it's syntactically correct, the thresholds are checked to ensure that they're all in the range 0.0 and 1.0 inclusive, and the threshold list is sorted in ascending numeric order. if the threshold list is empty, it's set to the array \[0.0\].

## Syntax

    var observer = new IntersectionObserver(callback[, options]);

### Parameters

`callback`  
A function which is called when the percentage of the target element is visible crosses a threshold. The callback receives as input two parameters:

`entries`  
An array of [`IntersectionObserverEntry`](../intersectionobserverentry) objects, each representing one threshold which was crossed, either becoming more or less visible than the percentage specified by that threshold.

`observer`  
The [`IntersectionObserver`](../intersectionobserver) for which the callback is being invoked.

`options` <span class="badge inline optional">Optional</span>  
An optional object which customizes the observer. If `options` isn't specified, the observer uses the document's viewport as the root, with no margin, and a 0% threshold (meaning that even a one-pixel change is enough to trigger a callback). You can provide any combination of the following options:

`root`  
An [`Element`](../element) or [`Document`](../document) object which is an ancestor of the intended target, whose bounding rectangle will be considered the viewport. Any part of the target not visible in the visible area of the `root` is not considered visible.

`rootMargin`  
A string which specifies a set of offsets to add to the root's [bounding_box](https://developer.mozilla.org/en-US/docs/Glossary/bounding_box) when calculating intersections, effectively shrinking or growing the root for calculation purposes. The syntax is approximately the same as that for the CSS [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) property; see [The root element and root margin](#) in [Intersection Observer API](../intersection_observer_api) for more information on how the margin works and the syntax. The default is "0px 0px 0px 0px".

`threshold`  
Either a single number or an array of numbers between 0.0 and 1.0, specifying a ratio of intersection area to total bounding box area for the observed target. A value of 0.0 means that even a single visible pixel counts as the target being visible. 1.0 means that the entire target element is visible. See [Thresholds](../intersection_observer_api#thresholds) in [Intersection Observer API](../intersection_observer_api) for a more in-depth description of how thresholds are used. The default is a threshold of 0.0.

### Return value

A new [`IntersectionObserver`](../intersectionobserver) which can be used to watch for the visibility of a target element within the specified `root` crossing through any of the specified visibility `threshold`s. Call its [`observe()`](observe) method to begin watching for the visibility changes on a given target.

### Exceptions

`SyntaxError`  
The specified `rootMargin` is invalid.

`RangeError`  
One or more of the values in `threshold` is outside the range 0.0 to 1.0.

## Example

This example creates a new intersection observer which calls the function `myObserverCallback` every time the visible area of the element being observed changes by at least 10%.

    let observer = new IntersectionObserver(myObserverCallback,
                       {threshold: 0.1});

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/IntersectionObserver/#dom-intersectionobserver-intersectionobserver">Intersection Observer<br />
<span class="small">The definition of 'IntersectionObserver constructor' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`IntersectionObserver`

51

15

55

No

38

12.1

51

51

55

?

12.2

5.0

`document_as_root`

81

81

76

No

68

No

81

81

No

58

No

13.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserver/IntersectionObserver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserver/IntersectionObserver</a>
