Save-Data
=========

The `Save-Data` header field is a boolean which, in requests, indicates the client's preference for reduced data usage. This could be for reasons such as high transfer costs, slow connection speeds, etc.

A value of `On` indicates explicit user opt-in into a reduced data usage mode on the client, and when communicated to origins allows them to deliver alternative content to reduce the data downloaded such as smaller image and video resources, different markup and styling, disabled polling and automatic updates, and so on.

**Note**: Disabling HTTP/2 Server Push ([RFC 7540, section 8.2: Server Push](https://tools.ietf.org/html/rfc7540#section-8.2)) might be desirable too for reducing data downloads.

Syntax
------

    Save-Data: <sd-token>

Directives
----------

`<sd-token>`  
A numerical value indicating whether the client wants to opt in to reduced data usage mode. `on` indicates yes, while `off` (the default) indicates no.

Examples
--------

The [`Vary`](vary) header ensures that the content is cached properly (for instance ensuring that the user is not served a lower-quality image from the cache when `Save-Data` header is no longer present \[*e.g.* after having switched from cellular to Wi-Fi\]).

### With `Save-Data: on`

Request:

    GET /image.jpg HTTP/1.0
    Host: example.com
    Save-Data: on

Response:

    HTTP/1.0 200 OK
    Content-Length: 102832
    Vary: Accept-Encoding, Save-Data
    Cache-Control: public, max-age=31536000
    Content-Type: image/jpeg

    [...]

### Without `Save-Data`

Request:

    GET /image.jpg HTTP/1.0
    Host: example.com

Response:

    HTTP/1.0 200 OK
    Content-Length: 481770
    Vary: Accept-Encoding, Save-Data
    Cache-Control: public, max-age=31536000
    Content-Type: image/jpeg

    [...]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/draft-grigorik-http-client-hints-03#section-7">draft-grigorik-http-client-hints-03, section 7: Save-Data</a></td><td>HTTP Client Hints</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Save-Data`

49

≤79

?

?

35

?

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Save-Data`

49

49

?

35

?

5.0

See also
--------

-   [Help Your Users \`Save-Data\` - CSS Tricks](https://css-tricks.com/help-users-save-data/)
-   [Delivering Fast and Light Applications with Save-Data - Google Developers](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/save-data/)
-   Header to indicate that the content served varies by `Save-Data`: [`Vary`](vary)
-   CSS @media feature `prefers-reduced-data`

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Save-Data$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Save-Data" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Save-Data</a>
