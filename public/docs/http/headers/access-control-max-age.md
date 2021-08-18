Access-Control-Max-Age
======================

The `Access-Control-Max-Age` response header indicates how long the results of a [preflight request](https://developer.mozilla.org/en-US/docs/Glossary/preflight_request) (that is the information contained in the [`Access-Control-Allow-Methods`](access-control-allow-methods) and [`Access-Control-Allow-Headers`](access-control-allow-headers) headers) can be cached.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Access-Control-Max-Age: <delta-seconds>

Directives
----------

&lt;delta-seconds&gt;  
Maximum number of seconds the results can be cached.  
Firefox [caps this at 24 hours](https://dxr.mozilla.org/mozilla-central/rev/7ae377917236b7e6111146aa9fb4c073c0efc7f4/netwerk/protocol/http/nsCORSListenerProxy.cpp#1131) (86400 seconds).  
Chromium (prior to v76) [caps at 10 minutes](https://cs.chromium.org/chromium/src/services/network/public/cpp/cors/preflight_result.cc?l=36&rcl=52002151773d8cd9ffc5f557cd7cc880fddcae3e) (600 seconds).  
Chromium (starting in v76) [caps at 2 hours](https://cs.chromium.org/chromium/src/services/network/public/cpp/cors/preflight_result.cc?l=31&rcl=49e7c0b4886cac1f3d09dc046bd528c9c811a0fa) (7200 seconds).  
Chromium also specifies a default value of 5 seconds.  
A value of **-1** will disable caching, requiring a preflight OPTIONS check for all calls.

Examples
--------

Cache results of a preflight request for 10 minutes:

    Access-Control-Max-Age: 600 

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#http-access-control-max-age">Fetch<br />
<span class="small">The definition of 'Access-Control-Max-Age' in that specification.</span></a></td><td><span class="spec-Living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Access-Control-Max-Age`

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

`Access-Control-Max-Age`

2

Yes

4

12

3.2

Yes

See also
--------

-   [`Access-Control-Allow-Headers`](access-control-allow-headers)
-   [`Access-Control-Allow-Methods`](access-control-allow-methods)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Max-Age$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Max-Age" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Max-Age</a>
