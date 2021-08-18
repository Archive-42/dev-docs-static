CSP: object-src
===============

The HTTP [`Content-Security-Policy`](../content-security-policy) `object-src` directive specifies valid sources for the [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object), [`<embed>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed), and [`<applet>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/applet) elements.

To set allowed types for [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object), [`<embed>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed), and [`<applet>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/applet) elements, use the [`plugin-types`](plugin-types) directive.

Elements controlled by `object-src` are perhaps coincidentally considered legacy HTML elements and aren't receiving new standardized features (such as the security attributes `sandbox` or `allow` for `<iframe>`). Therefore it is [recommended](https://csp.withgoogle.com/docs/strict-csp.html) to restrict this fetch-directive (e.g. explicitly set `object-src 'none'` if possible).

<table><tbody><tr class="odd"><td>CSP version</td><td>1</td></tr><tr class="even"><td>Directive type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Fetch_directive">Fetch directive</a></td></tr><tr class="odd"><td><a href="default-src"><code>default-src</code></a> fallback</td><td>Yes. If this directive is absent, the user agent will look for the <code>default-src</code> directive.</td></tr></tbody></table>

Syntax
------

One or more sources can be allowed for the object-src policy:

    Content-Security-Policy: object-src <source>;
    Content-Security-Policy: object-src <source> <source>;

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

'&lt;hash-algorithm&gt;-&lt;base64-value&gt;'  
A sha256, sha384 or sha512 hash of scripts or styles. The use of this source consists of two portions separated by a dash: the encryption algorithm used to create the hash and the base64-encoded hash of the script or style. When generating the hash, don't include the &lt;script&gt; or &lt;style&gt; tags and note that capitalization and whitespace matter, including leading or trailing whitespace. See [unsafe inline script](script-src#Unsafe_inline_script) for an example. In CSP 2.0, this applied only to inline scripts. CSP 3.0 allows it in the case of `script-src` for external scripts.

Examples
--------

### Violation cases

Given this CSP header:

    Content-Security-Policy: object-src https://example.com/

The following [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object), [`<embed>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed), and [`<applet>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/applet) elements are blocked and won't load:

    <embed src="https://not-example.com/flash"></embed>
    <object data="https://not-example.com/plugin"></object> 
    <applet archive="https://not-example.com/java"></applet>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-csp/#directive-object-src">Content Security Policy Level 3<br />
<span class="small">The definition of 'object-src' in that specification.</span></a></td><td><span class="spec-WD">Working Draft</span></td><td>No changes.</td></tr><tr class="even"><td><a href="https://w3c.github.io/webappsec-csp/2/#directive-object-src">Content Security Policy Level 2<br />
<span class="small">The definition of 'object-src' in that specification.</span></a></td><td><span class="spec-REC">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`object-src`

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

`object-src`

Yes

Yes

23

?

7

Yes

See also
--------

-   [`Content-Security-Policy`](../content-security-policy)
-   [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object), [`<embed>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed), and [`<applet>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/applet)
-   [`plugin-types`](plugin-types)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/object-src$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/object-src" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/object-src</a>
