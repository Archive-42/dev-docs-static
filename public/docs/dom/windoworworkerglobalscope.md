WindowOrWorkerGlobalScope
=========================

The `WindowOrWorkerGlobalScope` mixin describes several features common to the [`Window`](window) and [`WorkerGlobalScope`](workerglobalscope) interfaces. Each of these interfaces can, of course, add more features in addition to the ones listed below.

**Note**: `WindowOrWorkerGlobalScope` is a mixin and not an interface; you can't actually create an object of type `WindowOrWorkerGlobalScope`.

Properties
----------

These properties are defined on the [`WindowOrWorkerGlobalScope`](windoworworkerglobalscope) mixin, and implemented by [`Window`](window) and [`WorkerGlobalScope`](workerglobalscope).

 [`WindowOrWorkerGlobalScope.caches`](windoworworkerglobalscope/caches) <span class="badge inline readonly">Read only </span>   
Returns the [`CacheStorage`](cachestorage) object associated with the current context. This object enables functionality such as storing assets for offline use, and generating custom responses to requests.

 [`WindowOrWorkerGlobalScope.crossOriginIsolated`](windoworworkerglobalscope/crossoriginisolated) <span class="badge inline readonly">Read only </span>   
Returns a boolean value that indicates whether a [`SharedArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer) can be sent via a [`Window.postMessage()`](window/postmessage) call.

 [`WindowOrWorkerGlobalScope.indexedDB`](windoworworkerglobalscope/indexeddb) <span class="badge inline readonly">Read only </span>   
Provides a mechanism for applications to asynchronously access capabilities of indexed databases; returns an [`IDBFactory`](idbfactory) object.

 [`WindowOrWorkerGlobalScope.isSecureContext`](windoworworkerglobalscope/issecurecontext) <span class="badge inline readonly">Read only </span>   
Returns a boolean indicating whether the current context is secure (`true`) or not (`false`).

 [`WindowOrWorkerGlobalScope.origin`](windoworworkerglobalscope/origin) <span class="badge inline readonly">Read only </span>   
Returns the origin of the global scope, serialized as a string.

Methods
-------

These methods are defined on the [`WindowOrWorkerGlobalScope`](windoworworkerglobalscope) mixin, and implemented by [`Window`](window) and [`WorkerGlobalScope`](workerglobalscope).

[`WindowOrWorkerGlobalScope.atob()`](windoworworkerglobalscope/atob)  
Decodes a string of data which has been encoded using base-64 encoding.

[`WindowOrWorkerGlobalScope.btoa()`](windoworworkerglobalscope/btoa)  
Creates a base-64 encoded ASCII string from a string of binary data.

[`WindowOrWorkerGlobalScope.clearInterval()`](windoworworkerglobalscope/clearinterval)  
Cancels the repeated execution set using [`WindowOrWorkerGlobalScope.setInterval()`](windoworworkerglobalscope/setinterval).

[`WindowOrWorkerGlobalScope.clearTimeout()`](windoworworkerglobalscope/cleartimeout)  
Cancels the delayed execution set using [`WindowOrWorkerGlobalScope.setTimeout()`](windoworworkerglobalscope/settimeout).

[`WindowOrWorkerGlobalScope.createImageBitmap()`](windoworworkerglobalscope/createimagebitmap)  
Accepts a variety of different image sources, and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves to an [`ImageBitmap`](imagebitmap). Optionally the source is cropped to the rectangle of pixels originating at *(*`sx`, `sy`*)* with width `sw`, and height `sh`.

[`WindowOrWorkerGlobalScope.fetch()`](windoworworkerglobalscope/fetch)  
Starts the process of fetching a resource from the network.

[`WindowOrWorkerGlobalScope.queueMicrotask()`](windoworworkerglobalscope/queuemicrotask)  
Enqueues a microtask—a short function to be executed after execution of the JavaScript code completes and control isn't being returned to a JavaScript caller, but before handling callbacks and other tasks. This lets your code run without interfering with other, possibly higher priority, code, but *before* the browser runtime regains control, potentially depending upon the work you need to complete.

[`WindowOrWorkerGlobalScope.setInterval()`](windoworworkerglobalscope/setinterval)  
Schedules a function to execute every time a given number of milliseconds elapses.

[`WindowOrWorkerGlobalScope.setTimeout()`](windoworworkerglobalscope/settimeout)  
Schedules a function to execute in a given amount of time.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#windoworworkerglobalscope-mixin">HTML Living Standard<br />
<span class="small">The definition of '<code>WindowOrWorkerGlobalScope</code> mixin' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>This is where the main mixin is defined.</td></tr></tbody></table>

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

`WindowOrWorkerGlobalScope`

4

12

1

Yes

Yes

Yes

≤37

18

4

Yes

Yes

1.0

`atob`

4

12

1

27

`atob()` ignores all space characters in the argument to comply with the latest HTML5 spec (see [bug 711180](https://bugzil.la/711180)).

10

10.5

3

≤37

18

4

27

`atob()` ignores all space characters in the argument to comply with the latest HTML5 spec (see [bug 711180](https://bugzil.la/711180)).

11

1

1.0

`btoa`

4

12

1

10

10.5

3

≤37

18

4

11

1

1.0

`caches`

40

≤79

42

No

?

No

40

Yes

42

Yes

Yes

Yes

`clearInterval`

4

12

1

4

From Internet Explorer 4 through 8, `clearInterval` is an Object rather than a Function. This behavior was fixed in Internet Explorer 9.

4

4

1

18

4

10.1

1

1.0

`clearTimeout`

45

12

1

4

From Internet Explorer 4 through 8, `clearTimeout` is an Object rather than a Function. This behavior was fixed in Internet Explorer 9.

4

4

45

45

4

10.1

1

5.0

`createImageBitmap`

50

79

42

No

Yes

No

50

50

Yes

Yes

No

5.0

`crossOriginIsolated`

87

87

72

No

73

No

No

87

No

No

No

14.0

`fetch`

42

14

39

No

29

10.1

42

42

39

29

10.3

4.0

`indexedDB`

24

12

16

10

10

15

7

≤37

25

22

14

8

2.0

`isSecureContext`

55

≤79

52

?

?

?

55

55

52

?

?

6.0

`origin`

59

≤79

54

No

No

11

59

59

54

No

11

7.0

`queueMicrotask`

71

79

69

No

58

12.1

71

71

No

50

12.2

10.0

`setInterval`

30

12

1

4

4

1

4.4

30

4

10.1

1

3.0

`setTimeout`

30

12

1

4

4

1

4.4

30

4

10.1

1

3.0

See also
--------

-   [`Window`](window)
-   [`WorkerGlobalScope`](workerglobalscope)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope</a>
