If-Modified-Since
=================

The `If-Modified-Since` request HTTP header makes the request conditional: the server will send back the requested resource, with a [`200`](../status/200) status, only if it has been last modified after the given date. If the request has not been modified since, the response will be a [`304`](../status/304) without any body; the [`Last-Modified`](last-modified) response header of a previous request will contain the date of last modification. Unlike [`If-Unmodified-Since`](if-unmodified-since), `If-Modified-Since` can only be used with a [`GET`](../methods/get) or [`HEAD`](../methods/head).

When used in combination with [`If-None-Match`](if-none-match), it is ignored, unless the server doesn't support `If-None-Match`.

The most common use case is to update a cached entity that has no associated [`ETag`](etag).

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    If-Modified-Since: <day-name>, <day> <month> <year> <hour>:<minute>:<second> GMT

Directives
----------

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

    If-Modified-Since: Wed, 21 Oct 2015 07:28:00 GMT 

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7232#section-3.3">RFC 7232, section 3.3: If-Modified-Since</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Conditional Requests</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`If-Modified-Since`

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

`If-Modified-Since`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`ETag`](etag)
-   [`If-Unmodified-since`](if-unmodified-since)
-   [`If-Match`](if-match)
-   [`If-None-Match`](if-none-match)
-   [`304`](../status/304)` Not Modified`

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/If-Modified-Since$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/If-Modified-Since" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/If-Modified-Since</a>
