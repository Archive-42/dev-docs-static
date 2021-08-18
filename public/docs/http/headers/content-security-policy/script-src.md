CSP: script-src
===============

The HTTP [`Content-Security-Policy`](../content-security-policy) (CSP) `script-src` directive specifies valid sources for JavaScript. This includes not only URLs loaded directly into [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) elements, but also things like inline script event handlers (`onclick`) and [XSLT stylesheets](https://developer.mozilla.org/en-US/docs/Web/XSLT) which can trigger script execution.

<table><tbody><tr class="odd"><td>CSP version</td><td>1</td></tr><tr class="even"><td>Directive type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Fetch_directive">Fetch directive</a></td></tr><tr class="odd"><td><a href="default-src"><code>default-src</code></a> fallback</td><td>Yes. If this directive is absent, the user agent will look for the <code>default-src</code> directive.</td></tr></tbody></table>

Syntax
------

One or more sources can be allowed for the `script-src` policy:

    Content-Security-Policy: script-src <source>;
    Content-Security-Policy: script-src <source> <source>;

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

<!-- -->

'strict-dynamic'  
The `strict-dynamic` source expression specifies that the trust explicitly given to a script present in the markup, by accompanying it with a nonce or a hash, shall be propagated to all the scripts loaded by that root script. At the same time, any allow-list or source expressions such as `'self'` or `'unsafe-inline'` are ignored. See [script-src](script-src#strict-dynamic) for an example.

<!-- -->

'report-sample'  
Requires a sample of the violating code to be included in the violation report.

Examples
--------

### Violation case

Given this CSP header:

    Content-Security-Policy: script-src https://example.com/

the following script is blocked and won't be loaded or executed:

    <script src="https://not-example.com/js/library.js"></script>

Note that inline event handlers are blocked as well:

    <button id="btn" onclick="doSomething()">

You should replace them with [`addEventListener`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener) calls:

    document.getElementById("btn").addEventListener('click', doSomething);

### Unsafe inline script

**Note:** Disallowing inline styles and inline scripts is one of the biggest security wins CSP provides. However, if you absolutely have to use it, there are a few mechanisms that will allow them.

To allow inline scripts and inline event handlers, `'unsafe-inline'`, a nonce-source or a hash-source that matches the inline block can be specified.

    Content-Security-Policy: script-src 'unsafe-inline';

The above Content Security Policy will allow inline [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) elements

    <script> 
      var inline = 1; 
    </script>

You can use a nonce-source to only allow specific inline script blocks:

    Content-Security-Policy: script-src 'nonce-2726c7f26c'

You will have to set the same nonce on the [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) element:

    <script nonce="2726c7f26c">
      var inline = 1;
    </script>

Alternatively, you can create hashes from your inline scripts. CSP supports sha256, sha384 and sha512.

    Content-Security-Policy: script-src 'sha256-B2yPHKaXnvFWtRChIbabYmUBFZdVfKKXHbWtWidDVF8='

When generating the hash, don't include the [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) tags and note that capitalization and whitespace matter, including leading or trailing whitespace.

    <script>var inline = 1;</script>

### Unsafe eval expressions

The `'unsafe-eval'` source expression controls several script execution methods that create code from strings. If `'unsafe-eval'` isn't specified with the `script-src` directive, the following methods are blocked and won't have any effect:

-   [`eval()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/eval)
-   [`Function()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function)
-   When passing a string literal like to methods like: `window.setTimeout("alert(\"Hello World!\");", 500);`
    -   [`window.setTimeout`](https://developer.mozilla.org/en-US/docs/Web/API/Window/setTimeout)
    -   [`window.setInterval`](https://developer.mozilla.org/en-US/docs/Web/API/Window/setInterval)
    -   [`window.setImmediate`](https://developer.mozilla.org/en-US/docs/Web/API/Window/setImmediate)
-   [`window.execScript`](https://developer.mozilla.org/en-US/docs/Web/API/Window/execScript) (IE &lt; 11 only)

### strict-dynamic

The `'strict-dynamic'` source expression specifies that the trust explicitly given to a script present in the markup, by accompanying it with a nonce or a hash, shall be propagated to all the scripts loaded by that root script. At the same time, any whitelist or source expressions such as `'self'` or `'unsafe-inline'` will be ignored. For example, a policy such as `script-src 'strict-dynamic' 'nonce-R4nd0m' https://whitelisted.com/` would allow loading of a root script with `<script nonce="R4nd0m" src="https://example.com/loader.js">` and propagate that trust to any script loaded by `loader.js`, but disallow loading scripts from `https://whitelisted.com/` unless accompanied by a nonce or loaded from a trusted script.

    script-src 'strict-dynamic' 'nonce-someNonce'

*Or*

    script-src 'strict-dynamic' 'sha256-base64EncodedHash'

It is possible to deploy `strict-dynamic` in a backwards compatible way, without requiring user-agent sniffing.  
The policy:

    script-src 'unsafe-inline' https: 'nonce-abcdefg' 'strict-dynamic'

will act like `'unsafe-inline' https:` in browsers that support CSP1, `https: 'nonce-abcdefg'` in browsers that support CSP2, and `'nonce-abcdefg' 'strict-dynamic'` in browsers that support CSP3.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-csp/#directive-script-src">Content Security Policy Level 3<br />
<span class="small">The definition of 'script-src' in that specification.</span></a></td><td><span class="spec-WD">Working Draft</span></td><td>No changes.</td></tr><tr class="even"><td><a href="https://w3c.github.io/webappsec-csp/2/#directive-script-src">Content Security Policy Level 2<br />
<span class="small">The definition of 'script-src' in that specification.</span></a></td><td><span class="spec-REC">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`script-src`

25

14

23

No

15

7

With external scripts

59

≤79

?

No

?

?

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`script-src`

Yes

Yes

23

?

7

Yes

With external scripts

59

59

?

?

?

7.0

See also
--------

-   [`Content-Security-Policy`](../content-security-policy)
-   [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script)
-   [`script-src-elem`](script-src-elem)
-   [`script-src-attr`](script-src-attr)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/script-src$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/script-src" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/script-src</a>
