Date
====

The `Date` general HTTP header contains the date and time at which the message was originated.

Note that `Date` is listed in the [forbidden header names](https://fetch.spec.whatwg.org/#forbidden-header-name) in the fetch spec - so this code will not send `Date` header:

    fetch('https://httpbin.org/get', {
        'headers': {
            'Date': (new Date()).toUTCString()
        }
    })

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/General_header">General header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes</td></tr></tbody></table>

Syntax
------

    Date: <day-name>, <day> <month> <year> <hour>:<minute>:<second> GMT

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

GMT  
Greenwich Mean Time. HTTP dates are always expressed in GMT, never in local time.

Examples
--------

    Date: Wed, 21 Oct 2015 07:28:00 GMT 

    new Date().toUTCString()
    // "Mon, 09 Mar 2020 08:13:24 GMT"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7231#section-7.1.1.2">RFC 7231, section 7.1.1.2: Date</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Date`

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

`Date`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`Age`](age)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Date$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Date" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Date</a>
