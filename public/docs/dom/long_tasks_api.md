# Long Tasks API

## Motivation

The experimental Long Tasks API gives us visibility into tasks that take 50 milliseconds or more. The 50 ms threshold comes from the [RAIL Model](https://developers.google.com/web/fundamentals/performance/rail), in particular the ["Response: process events in under 50 ms"](https://developers.google.com/web/fundamentals/performance/rail#response) section.

Tasks that block the main thread for 50 ms or more cause, among other issues:

- Delayed "[Time to interactive](https://developer.mozilla.org/en-US/docs/Glossary/Time_to_interactive)".
- High/variable input latency.
- High/variable event handling latency.
- Janky animations and scrolling.

## Concepts

Some key terms or ideas that are utilized by the Long Tasks API.

### Long task

Any uninterrupted period where the main UI thread is busy for 50 ms or longer. Common examples include:

- Long running event handlers.
- Expensive reflows and other re-renders.
- Work the browser does between different turns of the event loop that exceeds 50 ms.

### Culprit browsing context container

The "culprit browsing context container", or "the container" for short, is the top level page, iframe, embed or object that the task occurred within.

### Attributions

A list of containers that the task occurred within. For tasks that don't occur within the top level page, the `containerId`, `containerName` and `containerSrc` fields may provide information as to the source of the task.

## Usage

    var observer = new PerformanceObserver(function(list) {
        var perfEntries = list.getEntries();
        for (var i = 0; i < perfEntries.length; i++) {
            // Process long task notifications:
            // report back for analytics and monitoring
            // ...
        }
    });
    // register observer for long task notifications
    observer.observe({entryTypes: ["longtask"]});
    // Long script execution after this will result in queueing
    // and receiving "longtask" entries in the observer.

## Interfaces

[`PerformanceLongTaskTiming`](performancelongtasktiming)  
Reports instances of long tasks.

[`TaskAttributionTiming`](taskattributiontiming)  
Returns information about the work involved in a long task and its associate frame context.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/longtasks/">Long Tasks API 1</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Long_Tasks_API`

58

≤79

No

See [bug 1348405](https://bugzil.la/1348405).

No

Yes

No

58

58

No

See [bug 1348405](https://bugzil.la/1348405).

Yes

No

7.0

`containerId`

58

≤79

No

No

Yes

No

58

58

No

Yes

No

7.0

`containerName`

58

≤79

No

No

Yes

No

58

58

No

Yes

No

7.0

`containerSrc`

58

≤79

No

No

Yes

No

58

58

No

Yes

No

7.0

`containerType`

58

≤79

No

No

Yes

No

58

58

No

Yes

No

7.0

`toJSON`

58

79

No

No

45

No

58

58

No

43

No

7.0

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

`Long_Tasks_API`

58

≤79

No

See [bug 1348405](https://bugzil.la/1348405).

No

Yes

No

58

58

No

See [bug 1348405](https://bugzil.la/1348405).

Yes

No

7.0

`attribution`

58

≤79

No

No

Yes

No

58

58

No

Yes

No

7.0

`toJSON`

58

79

No

No

45

No

58

58

No

43

No

7.0

BCD tables only load in the browser

### TaskAttributionTiming

BCD tables only load in the browser

## See also

- [GitHub repository](https://github.com/w3c/longtasks) contains documentation and some code samples.
- [PerfPlanet article](https://calendar.perfplanet.com/2017/tracking-cpu-with-long-tasks-api/) on Long Tasks API from 20th December 2017.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Long_Tasks_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Long_Tasks_API</a>
