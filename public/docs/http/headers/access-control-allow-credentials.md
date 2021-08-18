Access-Control-Allow-Credentials
================================

The `Access-Control-Allow-Credentials` response header tells browsers whether to expose the response to frontend JavaScript code when the request's credentials mode ([`Request.credentials`](https://developer.mozilla.org/en-US/docs/Web/API/Request/credentials)) is `include`.

When a request's credentials mode ([`Request.credentials`](https://developer.mozilla.org/en-US/docs/Web/API/Request/credentials)) is `include`, browsers will only expose the response to frontend JavaScript code if the `Access-Control-Allow-Credentials` value is `true`.

Credentials are cookies, authorization headers or TLS client certificates.

When used as part of a response to a preflight request, this indicates whether or not the actual request can be made using credentials. Note that simple [`GET`](../methods/get) requests are not preflighted, and so if a request is made for a resource with credentials, if this header is not returned with the resource, the response is ignored by the browser and not returned to web content.

The `Access-Control-Allow-Credentials` header works in conjunction with the [`XMLHttpRequest.withCredentials`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/withCredentials) property or with the `credentials` option in the [`Request()`](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request) constructor of the Fetch API. For a CORS request with credentials, in order for browsers to expose the response to frontend JavaScript code, both the server (using the `Access-Control-Allow-Credentials` header) and the client (by setting the credentials mode for the XHR, Fetch, or Ajax request) must indicate that they’re opting in to including credentials.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Access-Control-Allow-Credentials: true

Directives
----------

true  
The only valid value for this header is `true` (case-sensitive). If you don't need credentials, omit this header entirely (rather than setting its value to `false`).

Examples
--------

Allow credentials:

    Access-Control-Allow-Credentials: true

Using [XHR](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest) with credentials:

    var xhr = new XMLHttpRequest();
    xhr.open('GET', 'http://example.com/', true); 
    xhr.withCredentials = true; 
    xhr.send(null);

Using [Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) with credentials:

    fetch(url, {
      credentials: 'include'
    })

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#http-access-control-allow-credentials">Fetch<br />
<span class="small">The definition of 'Access-Control-Allow-Credentials' in that specification.</span></a></td><td><span class="spec-Living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Access-Control-Allow-Credentials`

4

12

3.5

10

12

4

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Access-Control-Allow-Credentials`

2

Yes

4

12

3.2

Yes

See also
--------

-   [`XMLHttpRequest.withCredentials`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/withCredentials)
-   [`Request()`](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Credentials$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Credentials" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Credentials</a>
