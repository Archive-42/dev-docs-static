DNT
===

The `DNT` (**D**o **N**ot **T**rack) request header indicates the user's tracking preference. It lets users indicate whether they would prefer privacy rather than personalized content.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes</td></tr></tbody></table>

Syntax
------

    DNT: 0
    DNT: 1
    DNT: null

Directives
----------

0  
The user prefers to allow tracking on the target site.

1  
The user prefers not to be tracked on the target site.

null  
The user has not specified a preference about tracking.

Examples
--------

### Reading Do Not Track status from JavaScript

The user's DNT preference can also be read from JavaScript using the [`Navigator.doNotTrack`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/doNotTrack) property:

    navigator.doNotTrack; // "0" or "1"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/tracking-dnt/#dnt-header-field">Tracking Preference Expression (DNT)<br />
<span class="small">The definition of 'DNT Header Field for HTTP Requests' in that specification.</span></a></td><td><span class="spec-Obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`DNT`

23

12

4

9

Yes

6 — 12.1

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`DNT`

Yes

Yes

Yes

Yes

? — 12.2

Yes

See also
--------

-   [`Navigator.doNotTrack`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/doNotTrack)
-   [`Tk`](tk) header
-   [Do Not Track on Wikipedia](https://en.wikipedia.org/wiki/Do_Not_Track)
-   [What Does the "Track" in "Do Not Track" Mean? – EFF](https://www.eff.org/deeplinks/2011/02/what-does-track-do-not-track-mean)
-   [donottrack.us](https://donottrack.us/)
-   DNT browser settings help:
    -   [Firefox](https://www.mozilla.org/en-US/firefox/dnt/)
    -   [Chrome](https://support.google.com/chrome/answer/2790761)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/DNT$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/DNT" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/DNT</a>
