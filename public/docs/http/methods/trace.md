TRACE
=====

The `TRACE` performs a message loop-back test along the path to the target resource, providing a useful debugging mechanism.

The final recipient of the request should reflect the message received, excluding some fields described below, back to the client as the message body of a [`200`](../status/200) (`OK`) response with a [`Content-Type`](../headers/content-type) of `message/http`. The final recipient is either the origin server or the first server to receive a [`Max-Forwards`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Max-Forwards) value of 0 in the request.

<table><tbody><tr class="odd"><td>Request has body</td><td>No</td></tr><tr class="even"><td>Successful response has body</td><td>No</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Safe">Safe</a></td><td>Yes</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Idempotent">Idempotent</a></td><td>Yes</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Cacheable">Cacheable</a></td><td>No</td></tr><tr class="even"><td>Allowed in HTML forms</td><td>No</td></tr></tbody></table>

Syntax
------

    TRACE /index.html

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7231#section-4.3.8">RFC 7231, section 4.3.8: TRACE</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`TRACE`

?

?

?

?

?

?

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`TRACE`

?

?

?

?

?

?

See also
--------

-   [HTTP methods](../methods)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/TRACE$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/TRACE" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/TRACE</a>
