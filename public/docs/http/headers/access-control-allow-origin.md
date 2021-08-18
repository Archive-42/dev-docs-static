Access-Control-Allow-Origin
===========================

The `Access-Control-Allow-Origin` response header indicates whether the response can be shared with requesting code from the given [origin](https://developer.mozilla.org/en-US/docs/Glossary/origin).

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Access-Control-Allow-Origin: *
    Access-Control-Allow-Origin: <origin>
    Access-Control-Allow-Origin: null

Directives
----------

`*`  
For requests *without credentials*, the literal value "`*`" can be specified, as a wildcard; the value tells browsers to allow requesting code from any origin to access the resource. Attempting to use the wildcard with credentials [will result in an error](../cors/errors/corsnotsupportingcredentials).

`<origin>`  
Specifies an origin. Only a single origin can be specified. If the server supports clients from multiple origins, it must return the origin for the specific client making the request.

`null`  
Specifies the origin "null".

**Note:** `null` [should not be used](https://w3c.github.io/webappsec-cors-for-developers/#avoid-returning-access-control-allow-origin-null): "It may seem safe to return `Access-Control-Allow-Origin: "null"`, but the serialization of the Origin of any resource that uses a non-hierarchical scheme (such as `data:` or `file:`) and sandboxed documents is defined to be "null". Many User Agents will grant such documents access to a response with an `Access-Control-Allow-Origin: "null"` header, and any origin can create a hostile document with a "null" Origin. The "null" value for the ACAO header should therefore be avoided."

Examples
--------

A response that tells the browser to allow code from any origin to access a resource will include the following:

    Access-Control-Allow-Origin: *

A response that tells the browser to allow requesting code from the origin `https://developer.mozilla.org` to access a resource will include the following:

    Access-Control-Allow-Origin: https://developer.mozilla.org

Limiting the possible `Access-Control-Allow-Origin` values to a set of allowed origins requires code on the server side to check the value of the [`Origin`](origin) request header, compare that to a list of allowed origins, and then if the [`Origin`](origin) value is in the list, to set the `Access-Control-Allow-Origin` value to the same value as the [`Origin`](origin) value.

### CORS and caching

If the server sends a response with an `Access-Control-Allow-Origin` value that is an explicit origin (rather than the "`*`" wildcard), then the response should also include a [`Vary`](vary) response header with the value `Origin` — to indicate to browsers that server responses can differ based on the value of the `Origin` request header.

    Access-Control-Allow-Origin: https://developer.mozilla.org
    Vary: Origin

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#http-access-control-allow-origin">Fetch<br />
<span class="small">The definition of 'Access-Control-Allow-Origin' in that specification.</span></a></td><td><span class="spec-Living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Access-Control-Allow-Origin`

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

`Access-Control-Allow-Origin`

2

Yes

4

12

3.2

Yes

See also
--------

-   [`Origin`](origin)
-   [`Vary`](vary)
-   [Cross-Origin Resource Sharing (CORS)](../cors)
-   [`Cross-Origin-Resource-Policy`](cross-origin-resource-policy)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Origin$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Origin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Origin</a>
