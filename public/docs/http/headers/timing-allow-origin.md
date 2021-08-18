Timing-Allow-Origin
===================

The `Timing-Allow-Origin` response header specifies origins that are allowed to see values of attributes retrieved via features of the [Resource Timing API](https://developer.mozilla.org/en-US/docs/Web/API/Resource_Timing_API), which would otherwise be reported as zero due to cross-origin restrictions.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Timing-Allow-Origin: *
    Timing-Allow-Origin: <origin>[, <origin>]*

Directives
----------

\*  
The server may specify "\*" as a wildcard, thereby allowing any origin to see timing resources.

&lt;origin&gt;  
Specifies a URI that may see the timing resources. You can specify multiple origins, separated by commas.

Examples
--------

To allow any resource to see timing resources:

    Timing-Allow-Origin: *

To allow `https://developer.mozilla.org` to see timing resources, you can specify:

    Timing-Allow-Origin: https://developer.mozilla.org

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/resource-timing/#sec-timing-allow-origin">Resource Timing Level 3<br />
<span class="small">The definition of 'Timing-Allow-Origin' in that specification.</span></a></td><td><span class="spec-ED">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Timing-Allow-Origin`

Yes

≤79

Yes

?

Yes

Yes

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Timing-Allow-Origin`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [Resource Timing API](https://developer.mozilla.org/en-US/docs/Web/API/Resource_Timing_API)
-   [Using the Resource Timing API](https://developer.mozilla.org/en-US/docs/Web/API/Resource_Timing_API/Using_the_Resource_Timing_API)
-   [`Vary`](vary)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Timing-Allow-Origin$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Timing-Allow-Origin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Timing-Allow-Origin</a>
