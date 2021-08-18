CSP: base-uri
=============

The HTTP [`Content-Security-Policy`](../content-security-policy) `base-uri` directive restricts the URLs which can be used in a document's [`<base>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/base) element. If this value is absent, then any URI is allowed. If this directive is absent, the user agent will use the value in the [`<base>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/base) element.

<table><tbody><tr class="odd"><td>CSP version</td><td>2</td></tr><tr class="even"><td>Directive type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Document_directive">Document directive</a></td></tr><tr class="odd"><td><a href="default-src"><code>default-src</code></a> fallback</td><td>No. Not setting this allows any URL.</td></tr></tbody></table>

Syntax
------

One or more *sources* can be allowed for the base-uri policy:

    Content-Security-Policy: base-uri <source>;
    Content-Security-Policy: base-uri <source> <source>;

### Sources

While this directive uses the same arguments as other CSP directives, some of them don’t make sense for \`&lt;base&gt;\`, such as the keywords `'unsafe-inline'` and `'strict-dynamic'`

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

<!-- -->

'strict-dynamic'  
The `strict-dynamic` source expression specifies that the trust explicitly given to a script present in the markup, by accompanying it with a nonce or a hash, shall be propagated to all the scripts loaded by that root script. At the same time, any allow-list or source expressions such as `'self'` or `'unsafe-inline'` are ignored. See [script-src](script-src#strict-dynamic) for an example.

<!-- -->

'report-sample'  
Requires a sample of the violating code to be included in the violation report.

Examples
--------

### Meta tag configuration

    <meta http-equiv="Content-Security-Policy" content="base-uri 'self'">

### Apache configuration

    <IfModule mod_headers.c> 
    Header set Content-Security-Policy "base-uri 'self'";
    </IfModule>

### Nginx configuration

    add_header Content-Security-Policy "base-uri 'self';"

### Violation case

Since your domain isn't `example.com`, a [`<base>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/base) element with its `href` set to `https://example.com` will result in a CSP violation.

    <meta http-equiv="Content-Security-Policy" content="base-uri 'self'">
    <base href="https://example.com/">

    // Error: Refused to set the document's base URI to 'https://example.com/' 
    // because it violates the following Content Security Policy 
    // directive: "base-uri 'self'"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-csp/#directive-base-uri">Content Security Policy Level 3<br />
<span class="small">The definition of 'base-uri' in that specification.</span></a></td><td><span class="spec-WD">Working Draft</span></td><td>No changes.</td></tr><tr class="even"><td><a href="https://w3c.github.io/webappsec-csp/2/#directive-base-uri">Content Security Policy Level 2<br />
<span class="small">The definition of 'base-uri' in that specification.</span></a></td><td><span class="spec-REC">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found. Please contribute data for "http.headers.csp.base-uri" (depth: 1) to the [MDN compatibility data repository](https://github.com/mdn/browser-compat-data).

See also
--------

-   [`Content-Security-Policy`](../content-security-policy)
-   [`<base>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/base)
-   [`Node.baseURI`](https://developer.mozilla.org/en-US/docs/Web/API/Node/baseURI)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/base-uri$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/base-uri" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/base-uri</a>
