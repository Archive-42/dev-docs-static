PerformanceNavigationTiming
===========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `PerformanceNavigationTiming` interface provides methods and properties to store and retrieve metrics regarding the browser's document navigation events. For example, this interface can be used to determine how much time it takes to load or unload a document.

Properties
----------

This interface extends the following [`PerformanceEntry`](performanceentry) properties for navigation performance entry types by qualifying and constraining them as follows:

 [`PerformanceEntry.entryType`](performanceentry/entrytype) <span class="badge inline readonly">Read only </span>   
Returns `"navigation"`.

 [`PerformanceEntry.name`](performanceentry/name) <span class="badge inline readonly">Read only </span>   
Returns the [document's address](https://dom.spec.whatwg.org/#concept-document-url).

 [`PerformanceEntry.startTime`](performanceentry/starttime) <span class="badge inline readonly">Read only </span>   
Returns a [`DOMHighResTimeStamp`](domhighrestimestamp) with a value of "`0`".

 [`PerformanceEntry.duration`](performanceentry/duration) <span class="badge inline readonly">Read only </span>   
Returns a [`timestamp`](domhighrestimestamp) that is the difference between the [`PerformanceNavigationTiming.loadEventEnd`](performancenavigationtiming/loadeventend) and [`PerformanceEntry.startTime`](performanceentry/starttime) properties.

This interface also extends following [`PerformanceResourceTiming`](performanceresourcetiming) properties for navigation performance entry types by qualifying and constraining them as follows:

 [`PerformanceResourceTiming.initiatorType`](performanceresourcetiming/initiatortype)<span class="badge inline readonly">Read only </span>   
Returns `"navigation"`.

The interface also supports the following properties:

 [`PerformanceNavigationTiming.domComplete`](performancenavigationtiming/domcomplete) <span class="badge inline readonly">Read only </span>   
A [`DOMHighResTimeStamp`](domhighrestimestamp) representing a time value equal to the time immediately before the browser sets the current document readiness of the current document to *[complete](https://html.spec.whatwg.org/multipage/syntax.html#the-end)*.

 [`PerformanceNavigationTiming.domContentLoadedEventEnd`](performancenavigationtiming/domcontentloadedeventend) <span class="badge inline readonly">Read only </span>   
A [`DOMHighResTimeStamp`](domhighrestimestamp) representing the time value equal to the time immediately after the current document's [DOMContentLoaded](https://html.spec.whatwg.org/multipage/syntax.html#the-end) event completes.

 [`PerformanceNavigationTiming.domContentLoadedEventStart`](performancenavigationtiming/domcontentloadedeventstart) <span class="badge inline readonly">Read only </span>   
A [`DOMHighResTimeStamp`](domhighrestimestamp) representing the time value equal to the time immediately before the user agent fires the [DOMContentLoaded](https://html.spec.whatwg.org/multipage/syntax.html#the-end) event at the current document.

 [`PerformanceNavigationTiming.domInteractive`](performancenavigationtiming/dominteractive) <span class="badge inline readonly">Read only </span>   
A [`DOMHighResTimeStamp`](domhighrestimestamp) representing a [`timestamp`](domhighrestimestamp) representing the time value equal to the time immediately before the user agent sets the current document readiness of the current document to [interactive](https://html.spec.whatwg.org/multipage/syntax.html#the-end).

 [`PerformanceNavigationTiming.loadEventEnd`](performancenavigationtiming/loadeventend) <span class="badge inline readonly">Read only </span>   
A [`DOMHighResTimeStamp`](domhighrestimestamp) representing the time when the load event of the current document is completed.

 [`PerformanceNavigationTiming.loadEventStart`](performancenavigationtiming/loadeventstart) <span class="badge inline readonly">Read only </span>   
A [`DOMHighResTimeStamp`](domhighrestimestamp) representing the time value equal to the time immediately before the load event of the current document is fired.

 [`PerformanceNavigationTiming.redirectCount`](performancenavigationtiming/redirectcount) <span class="badge inline readonly">Read only </span>   
A number representing the number of redirects since the last non-redirect navigation under the current browsing context.

If there was no redirect, or if the redirect was from another origin, and that origin does not permit it's timing information to be exposed to the current origin then the value will be 0.

 <span class="page-not-created">`PerformanceNavigationTiming.requestStart`</span> <span class="badge inline readonly">Read only </span>   
A [`DOMHighResTimeStamp`](domhighrestimestamp) representing the time immediately before the user agent starts requesting the resource from the server, or from relevant application caches or from local resources.

 <span class="page-not-created">`PerformanceNavigationTiming.responseStart`</span> <span class="badge inline readonly">Read only </span>   
A [`DOMHighResTimeStamp`](domhighrestimestamp) representing the time immediately after the user agent's HTTP parser receives the first byte of the response from relevant application caches, or from local resources or from the server.

 [`PerformanceNavigationTiming.type`](performancenavigationtiming/type) <span class="badge inline readonly">Read only </span>   
A [`string`](domstring) representing the navigation type. Must be: "`navigate`", "`reload`", "`back_forward`" or "`prerender`".

 [`PerformanceNavigationTiming.unloadEventEnd`](performancenavigationtiming/unloadeventend) <span class="badge inline readonly">Read only </span>   
A [`DOMHighResTimeStamp`](domhighrestimestamp) representing the time value equal to the time immediately after the user agent finishes the unload event of the previous document.

 [`PerformanceNavigationTiming.unloadEventStart`](performancenavigationtiming/unloadeventstart) <span class="badge inline readonly">Read only </span>   
A [`DOMHighResTimeStamp`](domhighrestimestamp) representing the time value equal to the time immediately before the user agent starts the unload event of the previous document.

Methods
-------

[`PerformanceNavigationTiming.toJSON()`](performancenavigationtiming/tojson)  
Returns a [`DOMString`](domstring) that is the JSON representation of the [`PerformanceNavigationTiming`](performancenavigationtiming) object.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/navigation-timing/#sec-PerformanceNavigationTiming">Navigation Timing Level 2<br />
<span class="small">The definition of 'PerformanceNavigationTiming' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PerformanceNavigationTiming`

57

12

58

You can disable this feature using the `dom.enable_performance_navigation_timing` preference (see [bug 1403926](https://bugzil.la/1403926)).

No

44

No

57

57

58

You can disable this feature using the `dom.enable_performance_navigation_timing` preference (see [bug 1403926](https://bugzil.la/1403926)).

43

No

7.0

`domComplete`

57

12

58

No

44

No

57

57

58

43

No

7.0

`domContentLoadedEventEnd`

57

12

58

No

44

No

57

57

58

43

No

7.0

`domContentLoadedEventStart`

57

12

58

No

44

No

57

57

58

43

No

7.0

`domInteractive`

57

12

58

No

44

No

57

57

58

43

No

7.0

`loadEventEnd`

57

12

58

No

44

No

57

57

58

43

No

7.0

`loadEventStart`

57

12

58

No

44

No

57

57

58

43

No

7.0

`redirectCount`

57

12

58

No

44

No

57

57

58

43

No

7.0

`toJSON`

57

≤18

58

No

44

No

57

57

58

43

No

7.0

`type`

57

12

58

No

44

No

57

57

58

43

No

7.0

`unloadEventEnd`

57

12

58

No

44

No

57

57

58

43

No

7.0

`unloadEventStart`

57

12

58

No

44

No

57

57

58

43

No

7.0

See also
--------

-   [`Performance.navigation`](performance/navigation)
-   [`PerformanceNavigation`](performancenavigation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceNavigationTiming" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceNavigationTiming</a>
