Cross-Origin-Embedder-Policy
============================

The HTTP `Cross-Origin-Embedder-Policy` (COEP) response header prevents a document from loading any cross-origin resources that don't explicitly grant the document permission (using [CORP](../cross-origin_resource_policy_(corp)) or [CORS](../cors)).

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Cross-Origin-Embedder-Policy: unsafe-none | require-corp

### Directives

`unsafe-none`  
This is the default value. Allows the document to fetch cross-origin resources without giving explicit permission through the CORS protocol or the [`Cross-Origin-Resource-Policy`](cross-origin-resource-policy) header.

`require-corp`  
A document can only load resources from the same origin, or resources explicitly marked as loadable from another origin.  
If a cross origin resource supports CORS, the `crossorigin` attribute or the [`Cross-Origin-Resource-Policy`](cross-origin-resource-policy) header must be used to load it without being blocked by COEP.

Examples
--------

### Certain features depend on cross-origin isolation

You can only access certain features like [`SharedArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer) objects or [`Performance.now()`](https://developer.mozilla.org/en-US/docs/Web/API/Performance/now) with unthrottled timers, if your document has a COEP header with the value `require-corp` value set.

    Cross-Origin-Embedder-Policy: require-corp
    Cross-Origin-Opener-Policy: same-origin

See also the [`Cross-Origin-Opener-Policy`](cross-origin-opener-policy) header which you'll need to set as well.

To check if cross origin isolation has been successful, you can test against the `crossOriginIsolated` property available to window and worker contexts:

    if (crossOriginIsolated) {
      // Post SharedArrayBuffer
    } else {
      // Do something else
    }

### Avoiding COEP blockage with CORS

If you enable COEP using `require-corp` and have a cross origin resource that needs to be loaded, it needs to support [CORS](../cors) and you need to explicitly mark the resource as loadable from another origin to avoid blockage from COEP. For example, you can use the `crossorigin` attribute for this image from a third-party site:

    <img src="https://thirdparty.com/img.png" crossorigin>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#coep">HTML Living Standard<br />
<span class="small">The definition of 'Cross-Origin-Embedder-Policy header' in that specification.</span></a></td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Cross-Origin-Embedder-Policy`

83

83

79

No

No

No

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Cross-Origin-Embedder-Policy`

No

83

79

No

No

No

See also
--------

-   [`Cross-Origin-Opener-Policy`](cross-origin-opener-policy)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cross-Origin-Embedder-Policy$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cross-Origin-Embedder-Policy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cross-Origin-Embedder-Policy</a>
