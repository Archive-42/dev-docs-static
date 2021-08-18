Server-Timing
=============

The `Server-Timing` header communicates one or more metrics and descriptions for a given request-response cycle. It is used to surface any backend server timing metrics (e.g. database read/write, CPU time, file system access, etc.) in the developer tools in the user's browser or in the [`PerformanceServerTiming`](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceServerTiming) interface.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

The syntax of the `Server-Timing` header allows you to communicate metrics in different ways: server metric name only, metric with value, metric with value and description, and metric with description.

The specification advices that names and descriptions should be kept as short as possible (use abbreviations and omit optional values where possible) to minimize the HTTP overhead.

    // Single metric without value
    Server-Timing: missedCache

    // Single metric with value
    Server-Timing: cpu;dur=2.4

    // Single metric with description and value
    Server-Timing: cache;desc="Cache Read";dur=23.2

    // Two metrics with value
    Server-Timing: db;dur=53, app;dur=47.2

    // Server-Timing as trailer
    Trailer: Server-Timing
    --- response body ---
    Server-Timing: total;dur=123.4

Privacy and security
--------------------

The `Server-Timing` header may expose potentially sensitive application and infrastructure information. Consider to control which metrics are returned when and to whom on the server side. For example, you could only show metrics to authenticated users and nothing to the public.

PerformanceServerTiming interface
---------------------------------

In addition to having `Server-Timing` header metrics appear in the developer tools of the browser, the [`PerformanceServerTiming`](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceServerTiming) interface enables tools to automatically collect and process metrics from JavaScript. This interface is restricted to the same origin, but you can use the [`Timing-Allow-Origin`](timing-allow-origin) header to specify the domains that are allowed to access the server metrics. The interface is only available in secure contexts (HTTPS) in some browsers.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/server-timing/#the-server-timing-header-field">Server Timing<br />
<span class="small">The definition of 'Server-Timing Header Field' in that specification.</span></a></td><td><span class="spec-WD">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Server-Timing`

65

≤79

61

No

52

?

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Server-Timing`

65

65

61

47

?

9.0

See also
--------

-   [`PerformanceServerTiming`](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceServerTiming)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Server-Timing$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Server-Timing" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Server-Timing</a>
