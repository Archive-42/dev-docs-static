IntersectionObserver.thresholds
===============================

**Draft**

This page is not complete.

The [`IntersectionObserver`](../intersectionobserver) interface's read-only `thresholds` property returns the list of intersection thresholds that was specified when the observer was instantiated with [`IntersectionObserver()`](intersectionobserver). If only one threshold ratio was provided when instanitating the object, this will be an array containing that single value.

See [Thresholds](../intersection_observer_api#thresholds) in [Intersection Observer API](../intersection_observer_api) to learn how thresholds work.

Syntax
------

    var thresholds = IntersectionObserver.thresholds;

### Value

An array of intersection thresholds, originally specified using the `threshold` property when instantiating the observer. If only one observer was specified, without being in an array, this value is a one-entry array containing that threshold. Regardless of the order your original `threshold` array was in, this one is always sorted in numerically increasing order.

If no `threshold` option was included when `IntersectionObserver()` was used to instantiate the observer, the value of `thresholds` is `[0]`.

Be careful! Although the `options` object you can specify when creating an [`IntersectionObserver`](../intersectionobserver) has a field named <span class="page-not-created">`threshold`</span>, this property is called `thresholds`. Confusing? Yes. If you accidentally use `thresholds` as the name of the field in your `options`, the `thresholds` array will wind up being `[0.0]`, which is likely not what you expect. Debugging chaos may ensue.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/IntersectionObserver/#dom-intersectionobserver-thresholds">Intersection Observer<br />
<span class="small">The definition of 'IntersectionObserver.thresholds' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`thresholds`

51

15

55

No

Yes

12.1

51

51

55

?

12.2

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserver/thresholds" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserver/thresholds</a>
