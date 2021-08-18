Navigation Timing API
=====================

The **Navigation Timing API** provides data that can be used to measure the performance of a web site. Unlike JavaScript-based libraries that have historically been used to collect similar information, the Navigation Timing API can be much more accurate and reliable.

**This article currently describes Navigation Timing Level 1.** There is a specification for Level 2, but it is not yet covered here.

Concepts and usage
------------------

You can use the Navigation Timing API to gather performance data on the client side, which you can then transmit to a server using [`XMLHttpRequest`](xmlhttprequest) or other techniques.

This API lets you measure data that was previously difficult to obtain, such as the amount of time needed to unload the previous page, how long domain lookups take, the total time spent executing the window's `load` handler, and so forth.

Interfaces
----------

[`Performance`](performance)  
The [`window.performance`](window/performance) property returns a `Performance` object. While this interface is defined by the High Resolution Time API, the Navigation Timing API adds two properties: [`timing`](performance/timing) and [`navigation`](performance/navigation), of the types below.

[`PerformanceNavigationTiming`](performancenavigationtiming)  
Provides methods and properties to store and retrieve metrics regarding the browser's document navigation events. For example, this interface can be used to determine how much time it takes to load or unload a document.

 <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceTiming`](performancetiming)   
Used as the type for the value of [`timing`](performance/timing), objects of this type contain timing information that can provide insight into web page performance.

 <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> [`PerformanceNavigation`](performancenavigation)   
The type used to return the value of [`navigation`](performance/navigation), which contains information explaining the context of the load operation described by this `Performance` instance.

The Navigation Timing API can be used to gather performance data on the client side to be sent to a server via XHR as well as measure data that was very difficult to measure by other means such as time to unload a previous page, domain look up time, `window.onload` total time, etc.

Examples
--------

### Calculate the total page load time

To compute the total amount of time it took to load the page, you can use the following code:

    const perfData = window.performance.timing;
    const pageLoadTime = perfData.loadEventEnd - perfData.navigationStart;

This subtracts the time at which navigation began ([`navigationStart`](performancetiming/navigationstart)) from the time at which the `load` event handler returns ([`loadEventEnd`](performancetiming/loadeventend)). This gives you the perceived page load time.

### Calculate request response time

You can calculate the time elapsed between the beginning of a request and the completion of getting the response using code like this:

    const connectTime = perfData.responseEnd - perfData.requestStart;

Here, the time at which the request was initiated ([`requestStart`](performancetiming/requeststart)). from the time at which the response was finished being received ([`responseEnd`](performancetiming/responseend)).

### Calculate page render time

As another example of an interesting piece of data you can obtain using the Navigation Timing API that you can't otherwise easily get, you can get the amount of time it took to render the page:

    const renderTime = perfData.domComplete - perfData.domLoading;

This is obtained by starting with the time at which loading of the DOM and its dependencies is complete ([`domComplete`](performancetiming/domcomplete)) and subtracting from it the time at which parsing of the DOM began ([`domLoading`](performancetiming/domloading)).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/navigation-timing/">Navigation Timing Level 2</a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds <code>PerformanceNavigationTiming</code></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/navigation-timing/">Navigation Timing</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Navigation_timing_API`

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

BCD tables only load in the browser

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigation_timing_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigation_timing_API</a>
