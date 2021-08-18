Cross-Origin-Opener-Policy
==========================

The HTTP `Cross-Origin-Opener-Policy` (COOP) response header allows you to ensure a top-level document does not share a browsing context group with cross-origin documents.

COOP will process-isolate your document and potential attackers can't access to your global object if they were opening it in a popup, preventing a set of cross-origin attacks dubbed [XS-Leaks](https://github.com/xsleaks/xsleaks).

If a cross-origin document with COOP is opened in a new window, the opening document will not have a reference to it, and the `window.opener` property of the new window will be `null`. This allows you to have more control over references to a window than `rel=noopener`, which only affects outgoing navigations.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Cross-Origin-Opener-Policy: unsafe-none | same-origin-allow-popups | same-origin

### Directives

`unsafe-none`  
This is the default value. Allows the document to be added to its opener's browsing context group unless the opener itself has a COOP of `same-origin` or `same-origin-allow-popups`.

`same-origin-allow-popups`  
Retains references to newly opened windows or tabs which either don't set COOP or which opt out of isolation by setting a COOP of `unsafe-none`.

`same-origin`  
Isolates the browsing context exclusively to same-origin documents. Cross-origin documents are not loaded in the same browsing context.

Examples
--------

### Certain features depend on cross-origin isolation

Certain features like [`SharedArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer) objects or [`Performance.now()`](https://developer.mozilla.org/en-US/docs/Web/API/Performance/now) with unthrottled timers are only available if your document has a COOP header with the value `same-origin` value set.

    Cross-Origin-Opener-Policy: same-origin
    Cross-Origin-Embedder-Policy: require-corp

See also the [`Cross-Origin-Embedder-Policy`](cross-origin-embedder-policy) header which you'll need to set as well.

To check if cross-origin isolation has been successful, you can test against the `crossOriginIsolated` property available to window and worker contexts:

    if (crossOriginIsolated) {
      // Post SharedArrayBuffer
    } else {
      // Do something else
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#the-cross-origin-opener-policy-header">HTML Living Standard<br />
<span class="small">The definition of 'Cross-Origin-Opener-Policy header' in that specification.</span></a></td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Cross-Origin-Opener-Policy`

83

83

79

79

67

Disabled

Disabled From version 67: this feature is behind the `browser.tabs.remote.useCrossOriginOpenerPolicy` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

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

`Cross-Origin-Opener-Policy`

No

83

79

79

67

Disabled

Disabled From version 67: this feature is behind the `browser.tabs.remote.useCrossOriginOpenerPolicy` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

No

No

See also
--------

-   [`Cross-Origin-Embedder-Policy`](cross-origin-embedder-policy)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cross-Origin-Opener-Policy$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cross-Origin-Opener-Policy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cross-Origin-Opener-Policy</a>
