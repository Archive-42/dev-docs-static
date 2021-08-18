# PerformanceTiming

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Warning**

This interface is deprecated in the [Navigation Timing Level 2 specification](https://w3c.github.io/navigation-timing/#obsolete). Please use the [`PerformanceNavigationTiming`](performancenavigationtiming) interface instead.

The `PerformanceTiming` interface is a legacy interface kept for backwards compatibility and contains properties that offer performance timing information for various events which occur during the loading and use of the current page. You get a `PerformanceTiming` object describing your page using the [`window.performance.timing`](performance/timing) property.

## Properties

_The `PerformanceTiming` interface doesn't inherit any properties._

These properties each describe the time at which a particular point in the page loading process was reached. Some correspond to DOM events; others describe the time at which internal browser operations of interest took place.

Each time is provided as a [Unix time](https://en.wikipedia.org/wiki/Unix_time) (`unsigned long long`) representing the moment, in milliseconds since the UNIX epoch.

These properties are listed in the order in which they occur during the navigation process.

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceTiming.navigationStart`](performancetiming/navigationstart) <span class="badge inline readonly">Read only </span>  
When the prompt for unload terminates on the previous document in the same browsing context. If there is no previous document, this value will be the same as `PerformanceTiming.fetchStart`.

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceTiming.unloadEventStart`](performancetiming/unloadeventstart) <span class="badge inline readonly">Read only </span>  
When the `unload` event has been thrown, indicating the time at which the previous document in the window began to unload. If there is no previous document, or if the previous document or one of the needed redirects is not of the same origin, the value returned is `0`.

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceTiming.unloadEventEnd`](performancetiming/unloadeventend) <span class="badge inline readonly">Read only </span>  
When the `unload` event handler finishes. If there is no previous document, or if the previous document, or one of the needed redirects, is not of the same origin, the value returned is `0`.

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceTiming.redirectStart`](performancetiming/redirectstart) <span class="badge inline readonly">Read only </span>  
When the first HTTP redirect starts. If there is no redirect, or if one of the redirects is not of the same origin, the value returned is `0`.

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceTiming.redirectEnd`](performancetiming/redirectend) <span class="badge inline readonly">Read only </span>  
When the last HTTP redirect is completed, that is when the last byte of the HTTP response has been received. If there is no redirect, or if one of the redirects is not of the same origin, the value returned is `0`.

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceTiming.fetchStart`](performancetiming/fetchstart) <span class="badge inline readonly">Read only </span>  
When the browser is ready to fetch the document using an HTTP request. This moment is _before_ the check to any application cache.

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceTiming.domainLookupStart`](performancetiming/domainlookupstart) <span class="badge inline readonly">Read only </span>  
When the domain lookup starts. If a persistent connection is used, or the information is stored in a cache or a local resource, the value will be the same as `PerformanceTiming.fetchStart`.

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceTiming.domainLookupEnd`](performancetiming/domainlookupend) <span class="badge inline readonly">Read only </span>  
When the domain lookup is finished. If a persistent connection is used, or the information is stored in a cache or a local resource, the value will be the same as `PerformanceTiming.fetchStart`.

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceTiming.connectStart`](performancetiming/connectstart) <span class="badge inline readonly">Read only </span>  
When the request to open a connection is sent to the network. If the transport layer reports an error and the connection establishment is started again, the last connection establishment start time is given. If a persistent connection is used, the value will be the same as `PerformanceTiming.fetchStart`.

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceTiming.connectEnd`](performancetiming/connectend) <span class="badge inline readonly">Read only </span>  
When the connection is opened network. If the transport layer reports an error and the connection establishment is started again, the last connection establishment end time is given. If a persistent connection is used, the value will be the same as `PerformanceTiming.fetchStart`. A connection is considered as opened when all secure connection handshake, or SOCKS authentication, is terminated.

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceTiming.secureConnectionStart`](performancetiming/secureconnectionstart) <span class="badge inline readonly">Read only </span>  
When the secure connection handshake starts. If no such connection is requested, it returns `0`.

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceTiming.requestStart`](performancetiming/requeststart) <span class="badge inline readonly">Read only </span>  
When the browser sent the request to obtain the actual document, from the server or from a cache. If the transport layer fails after the start of the request and the connection is reopened, this property will be set to the time corresponding to the new request.

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceTiming.responseStart`](performancetiming/responsestart) <span class="badge inline readonly">Read only </span>  
When the browser received the first byte of the response, from the server from a cache, or from a local resource.

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceTiming.responseEnd`](performancetiming/responseend) <span class="badge inline readonly">Read only </span>  
When the browser received the last byte of the response, or when the connection is closed if this happened first, from the server, the cache, or from a local resource.

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceTiming.domLoading`](performancetiming/domloading) <span class="badge inline readonly">Read only </span>  
When the parser started its work, that is when its [`Document.readyState`](document/readystate) changes to `'loading'` and the corresponding `readystatechange` event is thrown.

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceTiming.domInteractive`](performancetiming/dominteractive) <span class="badge inline readonly">Read only </span>  
When the parser finished its work on the main document, that is when its [`Document.readyState`](document/readystate) changes to `'interactive'` and the corresponding `readystatechange` event is thrown.

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceTiming.domContentLoadedEventStart`](performancetiming/domcontentloadedeventstart) <span class="badge inline readonly">Read only </span>  
Right before the parser sent the `DOMContentLoaded` event, that is right after all the scripts that need to be executed right after parsing have been executed.

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceTiming.domContentLoadedEventEnd`](performancetiming/domcontentloadedeventend) <span class="badge inline readonly">Read only </span>  
Right after all the scripts that need to be executed as soon as possible, in order or not, have been executed.

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceTiming.domComplete`](performancetiming/domcomplete) <span class="badge inline readonly">Read only </span>  
When the parser finished its work on the main document, that is when its [`Document.readyState`](document/readystate) changes to `'complete'` and the corresponding `readystatechange` event is thrown.

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceTiming.loadEventStart`](performancetiming/loadeventstart) <span class="badge inline readonly">Read only </span>  
When the `load` event was sent for the current document. If this event has not yet been sent, it returns `0.`

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceTiming.loadEventEnd`](performancetiming/loadeventend) <span class="badge inline readonly">Read only </span>  
When the `load` event handler terminated, that is when the load event is completed. If this event has not yet been sent, or is not yet completed, it returns `0.`

## Methods

_The `PerformanceTiming`_ _interface doesn't inherit any methods._

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="page-not-created">`PerformanceTiming.toJSON()`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Returns a [JSON object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON) representing this `PerformanceTiming` object.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/navigation-timing/#performancetiming">Navigation Timing<br />
<span class="small">The definition of 'PerformanceTiming' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PerformanceTiming`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

`connectEnd`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

`connectStart`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

`domainLookupEnd`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

`domainLookupStart`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

`domComplete`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

`domContentLoadedEventEnd`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

`domContentLoadedEventStart`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

`domInteractive`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

`domLoading`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

`fetchStart`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

`loadEventEnd`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

`loadEventStart`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

`navigationStart`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

`redirectEnd`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

`redirectStart`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

`requestStart`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

`responseEnd`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

`responseStart`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

`secureConnectionStart`

6

18

56

9

15

8

≤37

18

56

14

9

1.0

`toJSON`

44

12

25

9

32

10.1

44

44

25

32

10.3

4.0

`unloadEventEnd`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

`unloadEventStart`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

## See also

- The [`Performance.timing`](performance/timing) property that creates such an object.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming</a>
