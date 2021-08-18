If-Range
========

The `If-Range` HTTP request header makes a range request conditional: if the condition is fulfilled, the range request will be issued and the server sends back a [`206`](../status/206) `Partial Content` answer with the appropriate body. If the condition is not fulfilled, the full resource is sent back, with a [`200`](../status/200) `OK` status.

This header can be used either with a [`Last-Modified`](last-modified) validator, or with an [`ETag`](etag), but not with both.

The most common use case is to resume a download, to guarantee that the stored resource has not been modified since the last fragment has been received.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    If-Range: <day-name>, <day> <month> <year> <hour>:<minute>:<second> GMT
    If-Range: <etag>

Directives
----------

&lt;etag&gt;  
An entity tag uniquely representing the requested resource. It is a string of ASCII characters placed between double quotes (Like `"675af34563dc-tr34"`) and may be prefixed by `W/` to indicate that the weak comparison algorithm should be used.

<!-- -->

&lt;day-name&gt;  
One of "Mon", "Tue", "Wed", "Thu", "Fri", "Sat", or "Sun" (case-sensitive).

&lt;day&gt;  
2 digit day number, e.g. "04" or "23".

&lt;month&gt;  
One of "Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec" (case sensitive).

&lt;year&gt;  
4 digit year number, e.g. "1990" or "2016".

&lt;hour&gt;  
2 digit hour number, e.g. "09" or "23".

&lt;minute&gt;  
2 digit minute number, e.g. "04" or "59".

&lt;second&gt;  
2 digit second number, e.g. "04" or "59".

`GMT`  
Greenwich Mean Time. HTTP dates are always expressed in GMT, never in local time.

Examples
--------

    If-Range: Wed, 21 Oct 2015 07:28:00 GMT 

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7233#section-3.2">RFC 7233, section 3.2: If-Range</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Range Requests</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`If-Range`

Yes

12

Yes

Yes

Yes

Yes

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`If-Range`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`ETag`](etag)
-   [`Last-Modified`](last-modified)
-   [`If-Modified-Since`](if-modified-since)
-   [`If-Unmodified-Since`](if-unmodified-since)
-   [`If-Match`](if-match)
-   [`If-None-Match`](if-none-match)
-   [`206`](../status/206)` Partial Content`
-   [HTTP Conditional Requests](../conditional_requests)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/If-Range$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/If-Range" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/If-Range</a>
