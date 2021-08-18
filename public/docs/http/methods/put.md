PUT
===

The `PUT` creates a new resource or replaces a representation of the target resource with the request payload.

The difference between `PUT` and [`POST`](post) is that `PUT` is idempotent: calling it once or several times successively has the same effect (that is no *side* effect), whereas successive identical [`POST`](post) requests may have additional effects, akin to placing an order several times.

<table><tbody><tr class="odd"><td>Request has body</td><td>Yes</td></tr><tr class="even"><td>Successful response has body</td><td>No</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Safe">Safe</a></td><td>No</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Idempotent">Idempotent</a></td><td>Yes</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Cacheable">Cacheable</a></td><td>No</td></tr><tr class="even"><td>Allowed in <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms">HTML forms</a></td><td>No</td></tr></tbody></table>

Syntax
------

    PUT /new.html HTTP/1.1 

Example
-------

### Request

    PUT /new.html HTTP/1.1
    Host: example.com
    Content-type: text/html
    Content-length: 16

    <p>New File</p>

### Responses

If the target resource does not have a current representation and the `PUT` request successfully creates one, then the origin server must inform the user agent by sending a [`201`](../status/201) (`Created`) response.

    HTTP/1.1 201 Created
    Content-Location: /new.html

If the target resource does have a current representation and that representation is successfully modified in accordance with the state of the enclosed representation, then the origin server must send either a [`200`](../status/200) (`OK`) or a [`204`](../status/204) (`No Content`) response to indicate successful completion of the request.

    HTTP/1.1 204 No Content
    Content-Location: /existing.html

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7231#section-4.3.4">RFC 7231, section 4.3.4: PUT</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`PUT`

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

`PUT`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`201`](../status/201)
-   [`204`](../status/204)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PUT$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PUT" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PUT</a>
