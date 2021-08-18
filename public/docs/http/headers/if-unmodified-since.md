If-Unmodified-Since
===================

The `If-Unmodified-Since` request HTTP header makes the request conditional: the server will send back the requested resource, or accept it in the case of a [`POST`](../methods/post) or another non-[safe](https://developer.mozilla.org/en-US/docs/Glossary/safe) method, only if it has not been last modified after the given date. If the resource has been modified after the given date, the response will be a [`412`](../status/412) (Precondition Failed) error.

There are two common use cases:

-   In conjunction with non-[safe](https://developer.mozilla.org/en-US/docs/Glossary/safe) methods, like [`POST`](../methods/post), it can be used to implement an [optimistic concurrency control](https://en.wikipedia.org/wiki/Optimistic_concurrency_control), like done by some wikis: editions are rejected if the stored document has been modified since the original has been retrieved.
-   In conjunction with a range request with a [`If-Range`](if-range) header, it can be used to ensure that the new fragment requested comes from an unmodified document.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    If-Unmodified-Since: <day-name>, <day> <month> <year> <hour>:<minute>:<second> GMT

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

    If-Unmodified-Since: Wed, 21 Oct 2015 07:28:00 GMT 

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7232#section-3.4">RFC 7232, section 3.4: If-Unmodified-Since</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Conditional Requests</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`If-Unmodified-Since`

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

`If-Unmodified-Since`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`Last-Modified`](last-modified)
-   [`If-Modified-Since`](if-modified-since)
-   [`If-Match`](if-match)
-   [`If-None-Match`](if-none-match)
-   [`If-Range`](if-range)
-   [`412`](../status/412)` Precondition Failed`

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/If-Unmodified-Since$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/If-Unmodified-Since" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/If-Unmodified-Since</a>
