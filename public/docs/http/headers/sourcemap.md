SourceMap
=========

The `SourceMap` [HTTP](../index) response header links generated code to a [source map](https://developer.mozilla.org/en-US/docs/Tools/Debugger/How_to/Use_a_source_map), enabling the browser to reconstruct the original source and present the reconstructed original in the debugger.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    SourceMap: <url>
    X-SourceMap: <url> (deprecated)

### Directives

`<url>`  
A relative (to the request URL) or absolute URL pointing to a source map file.

Examples
--------

    SourceMap: /path/to/file.js.map

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://sourcemaps.info/spec.html">Draft document</a></td><td>Source Map Revision 3 Proposal</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`SourceMap`

Yes

Yes

Yes

Prefixed

Prefixed Implemented with the vendor prefix: X-

≤79

≤79

≤79

Prefixed

Prefixed Implemented with the vendor prefix: X-

55

55

27

Prefixed

Prefixed Implemented with the vendor prefix: X-

?

Yes

Yes

Yes

Prefixed

Prefixed Implemented with the vendor prefix: X-

Yes

Yes

Yes

Prefixed

Prefixed Implemented with the vendor prefix: X-

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`SourceMap`

Yes

Yes

Yes

Prefixed

Prefixed Implemented with the vendor prefix: X-

Yes

Yes

Yes

Prefixed

Prefixed Implemented with the vendor prefix: X-

55

55

27

Prefixed

Prefixed Implemented with the vendor prefix: X-

Yes

Yes

Yes

Prefixed

Prefixed Implemented with the vendor prefix: X-

Yes

Yes

Yes

Prefixed

Prefixed Implemented with the vendor prefix: X-

Yes

Yes

Yes

Prefixed

Prefixed Implemented with the vendor prefix: X-

See also
--------

-   [Firefox Developer Tools: using a source map](https://developer.mozilla.org/en-US/docs/Tools/Debugger/How_to/Use_a_source_map)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/SourceMap$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/SourceMap" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/SourceMap</a>
