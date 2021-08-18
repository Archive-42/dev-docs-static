CSP: frame-ancestors
====================

The HTTP [`Content-Security-Policy`](../content-security-policy) (CSP) `frame-ancestors` directive specifies valid parents that may embed a page using [`<frame>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frame), [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe), [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object), [`<embed>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed), or [`<applet>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/applet).

Setting this directive to `'none'` is similar to [`X-Frame-Options`](../x-frame-options)`: deny` (which is also supported in older browsers).

CSP version

2

Directive type

[Navigation directive](https://developer.mozilla.org/en-US/docs/Glossary/Navigation_directive)

[`default-src`](default-src) fallback

No. Not setting this allows anything.

This directive is not supported in the [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) element.

Syntax
------

One or more sources can be set for the `frame-ancestors` policy:

    Content-Security-Policy: frame-ancestors <source>;
    Content-Security-Policy: frame-ancestors <source> <source>;

### Sources

&lt;source&gt; can be one of the following:

The `frame-ancestors` directive’s syntax is similar to a source list of other directives (e.g. [`default-src`](default-src)), but doesn't allow `'unsafe-eval'` or `'unsafe-inline'` for example. It will also not fall back to a `default-src` setting. Only the sources listed below are allowed:

&lt;host-source&gt;  
Internet hosts by name or IP address, as well as an optional [URL scheme](https://developer.mozilla.org/en-US/docs/URIs_and_URLs) and/or port number, separated by spaces. The site's address may include an optional leading wildcard (the asterisk character, `'*'`), and you may use a wildcard (again, `'*'`) as the port number, indicating that all legal ports are valid for the source. Single quotes surrounding the host are not allowed.  
Examples:

-   `http://*.example.com`: Matches all attempts to load from any subdomain of example.com using the `http:` URL scheme.
-   `mail.example.com:443`: Matches all attempts to access port 443 on mail.example.com.
-   `https://store.example.com`: Matches all attempts to access store.example.com using `https:`.

If no URL scheme is specified for a `host-source` and the iframe is loaded from an `https` URL, the URL for the page loading the iframe must also be `https`, per the W3C spec on [matching source expressions](https://w3c.github.io/webappsec-csp/2/#match-source-expression).

&lt;scheme-source&gt;  
A scheme such as `http:` or `https:`. The colon is required and scheme should not be quoted. You can also specify data schemes (not recommended).

-   `data:` Allows [`data:` URIs](../../basics_of_http/data_uris) to be used as a content source. *This is insecure; an attacker can also inject arbitrary data: URIs. Use this sparingly and definitely not for scripts.*
-   `mediastream:` Allows [`mediastream:` URIs](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream_API) to be used as a content source.
-   `blob:` Allows [`blob:` URIs](https://developer.mozilla.org/en-US/docs/Web/API/Blob) to be used as a content source.
-   `filesystem:` Allows [`filesystem:` URIs](https://developer.mozilla.org/en-US/docs/Web/API/FileSystem) to be used as a content source.

`'self'`  
Refers to the origin from which the protected document is being served, including the same URL scheme and port number. You must include the single quotes. Some browsers specifically exclude `blob` and `filesystem` from source directives. Sites needing to allow these content types can specify them using the Data attribute.

`'none'`  
Refers to the empty set; that is, no URLs match. The single quotes are required.

Examples
--------

    Content-Security-Policy: frame-ancestors 'none';

    Content-Security-Policy: frame-ancestors 'self' https://www.example.org;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-csp/#directive-frame-ancestors">Content Security Policy Level 3<br />
<span class="small">The definition of 'frame-ancestors' in that specification.</span></a></td><td><span class="spec-WD">Working Draft</span></td><td>No changes.</td></tr><tr class="even"><td><a href="https://w3c.github.io/webappsec-csp/2/#directive-frame-ancestors">Content Security Policy Level 2<br />
<span class="small">The definition of 'frame-ancestors' in that specification.</span></a></td><td><span class="spec-REC">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`frame-ancestors`

40

15

33

 33   
Before Firefox 58, `frame-ancestors` is ignored in `Content-Security-Policy-Report-Only`.

No

26

10

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`frame-ancestors`

?

Yes

33

 33   
Before Firefox for Android 58, `frame-ancestors` is ignored in `Content-Security-Policy-Report-Only`.

?

9.3

Yes

See also
--------

-   [`Content-Security-Policy`](../content-security-policy)
-   [`X-Frame-Options`](../x-frame-options)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/frame-ancestors$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/frame-ancestors" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/frame-ancestors</a>
