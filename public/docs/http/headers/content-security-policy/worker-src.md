CSP: worker-src
===============

The HTTP [`Content-Security-Policy`](../content-security-policy) (CSP) `worker-src` directive specifies valid sources for [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker), [`SharedWorker`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker), or [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker) scripts.

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td>CSP version</td><td>3</td></tr><tr class="even"><td>Directive type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Fetch_directive">Fetch directive</a></td></tr><tr class="odd"><td>Fallback</td><td><p>If this directive is absent, the user agent will first look for the <a href="child-src"><code>child-src</code></a> directive, then the <a href="script-src"><code>script-src</code></a> directive, then finally for the <a href="default-src"><code>default-src</code></a> directive, when governing worker execution.</p><p>Chrome 59 and higher skips the <a href="child-src"><code>child-src</code></a> directive.</p><p>Edge 17 skips the <a href="script-src"><code>script-src</code></a> directive (<a href="https://developer.microsoft.com/en-us/microsoft-edge/platform/issues/17415478/">bug</a>).</p></td></tr></tbody></table>

Syntax
------

One or more sources can be allowed for the `worker-src` policy:

    Content-Security-Policy: worker-src <source>;
    Content-Security-Policy: worker-src <source> <source>;

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

    Content-Security-Policy: worker-src https://example.com/

[`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker), [`SharedWorker`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker), [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker) are blocked and won't load:

    <script> 
      var blockedWorker = new Worker("data:application/javascript,..."); 
      blockedWorker = new SharedWorker("https://not-example.com/"); 
      navigator.serviceWorker.register('https://not-example.com/sw.js'); 
    </script>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-csp/#directive-worker-src">Content Security Policy Level 3<br />
<span class="small">The definition of 'worker-src' in that specification.</span></a></td><td><span class="spec-WD">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`worker-src`

59

 59   
Chrome 59 and higher skips the deprecated `child-src` directive.

79

58

No

48

No

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`worker-src`

59

 59   
Chrome 59 and higher skips the deprecated `child-src` directive.

59

 59   
Chrome 59 and higher skips the deprecated `child-src` directive.

58

45

No

7.0

See also
--------

-   [`Content-Security-Policy`](../content-security-policy)
-   [CSP for Web Workers](https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers#Content_security_policy)
-   [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker), [`SharedWorker`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker), [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/worker-src$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/worker-src" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/worker-src</a>
