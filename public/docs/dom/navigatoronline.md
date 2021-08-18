NavigatorOnLine
===============

The `NavigatorOnLine` interface contains methods and properties related to the connectivity status of the browser.

There is no object of type `NavigatorOnLine`, but other interfaces, like [`Navigator`](navigator) or [`WorkerNavigator`](workernavigator), implement it.

Properties
----------

*The `NavigatorOnLine` interface doesn't inherit any property.*

 [`NavigatorOnLine.onLine`](navigatoronline/online) <span class="badge inline readonly">Read only </span>   
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the browser is working online.

Methods
-------

*The `NavigatorOnLine` interface neither implements, nor inherit any method.*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#browser-state">HTML Living Standard<br />
<span class="small">The definition of 'NavigatorOnLine' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`NavigatorOnLine`

1

12

1.5

4

3

4

1

18

4

10.1

3.2

1.0

`onLine`

1

Earlier versions of Chrome incorrectly return true when a tab is first opened, but it starts reporting the correct connectivity status after the first network event. Windows: 11, Mac: 14, Chrome OS: 13, Linux: Always returns `true`. For history, see [crbug.com/7469](https://crbug.com/7469).

12

1.5

Since Firefox 4 the browser returns `true` when 'Work Offline' mode is disabled and `false` when it is enabled, regardless of actual connectivity. Since Firefox 41, on OS X and Windows, the returned values follow the actual network connectivity, unless 'Work offline' mode is selected (where it will always return `false`).

4

in Internet Explorer 8 'online' and 'offline' events are raised on the `document.body`; under IE 9 they are raised on both `document.body` and `window`.

3

From Opera 11.1 until Opera 12.1, the browser returns `true` when 'Work Offline' mode is disabled and `false` when it is enabled, regardless of actual connectivity.

4

1

Faulty in a WebView component, see Issue [bug 16760](http://code.google.com/p/android/issues/detail?id=16760).

18

4

10.1

From Opera 11.1 until Opera 12.1, the browser returns `true` when 'Work Offline' mode is disabled and `false` when it is enabled, regardless of actual connectivity.

3.2

1.0

See also
--------

-   The [`Navigator`](navigator) interface that implements it.
-   [Online and offline events](navigatoronline/online_and_offline_events)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NavigatorOnLine" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NavigatorOnLine</a>
