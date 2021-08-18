CSP: default-src
================

The HTTP [`Content-Security-Policy`](../content-security-policy) (CSP) `default-src` directive serves as a fallback for the other CSP [fetch directives](https://developer.mozilla.org/en-US/docs/Glossary/fetch_directive). For each of the following directives that are absent, the user agent looks for the `default-src` directive and uses this value for it:

-   [`child-src`](child-src)
-   [`connect-src`](connect-src)
-   [`font-src`](font-src)
-   [`frame-src`](frame-src)
-   [`img-src`](img-src)
-   [`manifest-src`](manifest-src)
-   [`media-src`](media-src)
-   [`object-src`](object-src)
-   [`prefetch-src`](prefetch-src)
-   [`script-src`](script-src)
-   [`script-src-elem`](script-src-elem)
-   [`script-src-attr`](script-src-attr)
-   [`style-src`](style-src)
-   [`style-src-elem`](style-src-elem)
-   [`style-src-attr`](style-src-attr)
-   [`worker-src`](worker-src)

<table><tbody><tr class="odd"><td>CSP version</td><td>1</td></tr><tr class="even"><td>Directive type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Fetch_directive">Fetch directive</a></td></tr></tbody></table>

Syntax
------

One or more sources can be allowed for the `default-src` policy:

    Content-Security-Policy: default-src <source>;
    Content-Security-Policy: default-src <source> <source>;

### Sources

&lt;source&gt; can be one of the following:

&lt;host-source&gt;  
Internet hosts by name or IP address, as well as an optional [URL scheme](https://developer.mozilla.org/en-US/docs/URIs_and_URLs) and/or port number. The site's address may include an optional leading wildcard (the asterisk character, `'*'`), and you may use a wildcard (again, `'*'`) as the port number, indicating that all legal ports are valid for the source.  
Examples:

-   `http://*.example.com`: Matches all attempts to load from any subdomain of example.com using the `http:` URL scheme.
-   `mail.example.com:443`: Matches all attempts to access port 443 on mail.example.com.
-   `https://store.example.com`: Matches all attempts to access store.example.com using `https:`.
-   `*.example.com`: Matches all attempts to load from any subdomain of example.com using the current protocol.

&lt;scheme-source&gt;  
A scheme such as `http:` or `https:`. The colon is required. Unlike other values below, single quotes shouldn't be used. You can also specify data schemes (not recommended).

-   `data:` Allows [`data:` URIs](../../basics_of_http/data_uris) to be used as a content source. *This is insecure; an attacker can also inject arbitrary data: URIs. Use this sparingly and definitely not for scripts.*
-   `mediastream:` Allows [`mediastream:` URIs](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream_API) to be used as a content source.
-   `blob:` Allows [`blob:` URIs](https://developer.mozilla.org/en-US/docs/Web/API/Blob) to be used as a content source.
-   `filesystem:` Allows [`filesystem:` URIs](https://developer.mozilla.org/en-US/docs/Web/API/FileSystem) to be used as a content source.

`'self'`  
Refers to the origin from which the protected document is being served, including the same URL scheme and port number. You must include the single quotes. Some browsers specifically exclude `blob` and `filesystem` from source directives. Sites needing to allow these content types can specify them using the Data attribute.

`'unsafe-eval'`  
Allows the use of `eval()` and similar methods for creating code from strings. You must include the single quotes.

`'unsafe-hashes'`  
Allows enabling specific inline [event handlers](https://developer.mozilla.org/en-US/docs/Web/Guide/Events/Event_handlers). If you only need to allow inline event handlers and not inline [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) elements or `javascript:` URLs, this is a safer method than using the `unsafe-inline` expression.

`'unsafe-inline'`  
Allows the use of inline resources, such as inline [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) elements, `javascript:` URLs, inline event handlers, and inline [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style) elements. The single quotes are required.

`'none'`  
Refers to the empty set; that is, no URLs match. The single quotes are required.

'nonce-&lt;base64-value&gt;'  
An allow-list for specific inline scripts using a cryptographic nonce (number used once). The server must generate a unique nonce value each time it transmits a policy. It is critical to provide an unguessable nonce, as bypassing a resource’s policy is otherwise trivial. See [unsafe inline script](script-src#Unsafe_inline_script) for an example. Specifying nonce makes a modern browser ignore `'unsafe-inline'` which could still be set for older browsers without nonce support.

**Note:** The CSP `nonce` source can only be apply *nonceable* elements (e.g. as the [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element has no `nonce` attribute, there is no way to associate it with this CSP source).

'&lt;hash-algorithm&gt;-&lt;base64-value&gt;'  
A sha256, sha384 or sha512 hash of scripts or styles. The use of this source consists of two portions separated by a dash: the encryption algorithm used to create the hash and the base64-encoded hash of the script or style. When generating the hash, don't include the &lt;script&gt; or &lt;style&gt; tags and note that capitalization and whitespace matter, including leading or trailing whitespace. See [unsafe inline script](script-src#Unsafe_inline_script) for an example. In CSP 2.0, this applied only to inline scripts. CSP 3.0 allows it in the case of `script-src` for external scripts.

<!-- -->

'strict-dynamic'  
The `strict-dynamic` source expression specifies that the trust explicitly given to a script present in the markup, by accompanying it with a nonce or a hash, shall be propagated to all the scripts loaded by that root script. At the same time, any allow-list or source expressions such as `'self'` or `'unsafe-inline'` are ignored. See [script-src](script-src#strict-dynamic) for an example.

<!-- -->

'report-sample'  
Requires a sample of the violating code to be included in the violation report.

Examples
--------

### No inheritance with default-src

If there are other directives specified, `default-src` does not influence them. The following header:

    Content-Security-Policy: default-src 'self'; script-src https://example.com

is the same as:

    Content-Security-Policy: connect-src 'self'; 
                             font-src 'self'; 
                             frame-src 'self'; 
                             img-src 'self'; 
                             manifest-src 'self'; 
                             media-src 'self'; 
                             object-src 'self'; 
                             script-src https://example.com; 
                             style-src 'self'; 
                             worker-src 'self'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-csp/#directive-default-src">Content Security Policy Level 3<br />
<span class="small">The definition of 'default-src' in that specification.</span></a></td><td><span class="spec-WD">Working Draft</span></td><td>Added <code>frame-src</code>, <code>manifest-src</code> and <code>worker-src</code> as defaults.</td></tr><tr class="even"><td><a href="https://w3c.github.io/webappsec-csp/2/#directive-default-src">Content Security Policy Level 2<br />
<span class="small">The definition of 'default-src' in that specification.</span></a></td><td><span class="spec-REC">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`default-src`

25

14

23

No

15

7

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`default-src`

Yes

Yes

23

?

7

Yes

See also
--------

-   [`Content-Security-Policy`](../content-security-policy)
-   CSP directives (<https://www.w3.org/TR/CSP/#csp-directives>):
    -   [Fetch directive](https://developer.mozilla.org/en-US/docs/Glossary/Fetch_directive)
    -   [Document directive](https://developer.mozilla.org/en-US/docs/Glossary/Document_directive)
    -   [Navigation directive](https://developer.mozilla.org/en-US/docs/Glossary/Navigation_directive)
    -   [Reporting directive](https://developer.mozilla.org/en-US/docs/Glossary/Reporting_directive)
    -   `upgrade-insecure-requests`
    -   `block-all-mixed-content`
    -   `require-sri-for`

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/default-src$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/default-src" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/default-src</a>
