Window.performance
==================

The [`Window`](../window) interface's `performance` property returns a [`Performance`](../performance) object, which can be used to gather performance information about the current document. It serves as the point of exposure for the Performance Timeline API, the High Resolution Time API, the [Navigation Timing API](../navigation_timing_api), the [User Timing API](../user_timing_api), and the [Resource Timing API](../resource_timing_api).

Syntax
------

    performanceData = window.performance;

### Value

A [`Performance`](../performance) object offering access to the performance and timing-related information offered by the APIs it exposes.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/hr-time-1/#performance">High Resolution Time<br />
<span class="small">The definition of 'window.performance' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Defines <code>now()</code> method.</td></tr></tbody></table>

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

`performance`

6

12

7

9

15

8

Yes

Yes

7

14

9

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/performance" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/performance</a>
