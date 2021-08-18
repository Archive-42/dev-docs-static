NavigatorConcurrentHardware
===========================

The `NavigatorConcurrentHardware` [mixin](https://developer.mozilla.org/en-US/docs/Glossary/Mixin) adds to the [`Navigator`](navigator) interface features which allow Web content to determine how many logical processors the user has available, in order to let content and Web apps optimize their operations to best take advantage of the user's CPU.

**Note:** This feature is available in [Web Workers](web_workers_api).

The number of **logical processor cores** is a way to measure the number of threads which can effectively be run at once without them having to share CPUs. Modern computers have multiple physical cores in their CPU (two or four cores is typical), but each physical core is also usually able to run more than one thread at a time using advanced scheduling techniques. So a four-core CPU may return 8. The browser may, however, choose to reduce the number in order to represent more accurately the number of [`Worker`](worker)s that can run at once

Properties
----------

 [`NavigatorConcurrentHardware.hardwareConcurrency`](navigatorconcurrenthardware/hardwareconcurrency) <span class="badge inline readonly">Read only </span>   
Returns the number of logical processors which may be available to the user agent. This value is always at least 1, and will be 1 if the actual number of logical processors can't be determined.

Methods
-------

*The `NavigatorConcurrentHardware` mixin has no methods.*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#navigator.hardwareconcurrency">HTML Living Standard<br />
<span class="small">The definition of 'NavigatorConcurrentHardware' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`NavigatorConcurrentHardware`

37

15

48

No

24

10.1-11

37

37

48

24

10.3-11

3.0

`hardwareConcurrency`

37

15

48

No

24

10.1-11

37

37

48

24

10.3-11

3.0

See also
--------

-   [`Navigator`](navigator)
-   [`WorkerNavigator`](workernavigator)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NavigatorConcurrentHardware" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NavigatorConcurrentHardware</a>
