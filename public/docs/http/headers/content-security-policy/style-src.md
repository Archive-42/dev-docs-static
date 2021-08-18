CSP: style-src
==============

The HTTP [`Content-Security-Policy`](../content-security-policy) (CSP) `style-src` directive specifies valid sources for stylesheets.

<table><tbody><tr class="odd"><td>CSP version</td><td>1</td></tr><tr class="even"><td>Directive type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Fetch_directive">Fetch directive</a></td></tr><tr class="odd"><td><a href="default-src"><code>default-src</code></a> fallback</td><td>Yes. If this directive is absent, the user agent will look for the <code>default-src</code> directive.</td></tr></tbody></table>

Syntax
------

One or more sources can be allowed for the `style-src` policy:

    Content-Security-Policy: style-src <source>;
    Content-Security-Policy: style-src <source> <source>;

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

    Content-Security-Policy: style-src https://example.com/

the following stylesheets are blocked and won't load:

    <link href="https://not-example.com/styles/main.css" rel="stylesheet" type="text/css" />

    <style>
    #inline-style { background: red; }
    </style>

    <style>
      @import url("https://not-example.com/styles/print.css") print;
    </style>

as well as styles loaded using the [`Link`](../link) header:

    Link: <https://not-example.com/styles/stylesheet.css>;rel=stylesheet

Inline style attributes are also blocked:

    <div style="display:none">Foo</div>

As well as styles that are applied in JavaScript by setting the `style` attribute directly, or by setting [`cssText`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/cssText):

    document.querySelector('div').setAttribute('style', 'display:none;');
    document.querySelector('div').style.cssText = 'display:none;';

However, styles properties that are set directly on the element's [`style`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style) property will not be blocked, allowing users to safely manipulate styles via JavaScript:

    document.querySelector('div').style.display = 'none';

These types of manipulations can be prevented by disallowing Javascript via the [`script-src`](script-src) CSP directive.

### Unsafe inline styles

**Note:** Disallowing inline styles and inline scripts is one of the biggest security wins CSP provides. However, if you absolutely have to use it, there are a few mechanisms that will allow them.

To allow inline styles, `'unsafe-inline'`, a nonce-source or a hash-source that matches the inline block can be specified.

    Content-Security-Policy: style-src 'unsafe-inline';

The above Content Security Policy will allow inline styles like the [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style) element, and the `style` attribute on any element:

    <style>
      #inline-style { background: red; }
    </style>

    <div style="display:none">Foo</div>

You can use a nonce-source to only allow specific inline style blocks:

    Content-Security-Policy: style-src 'nonce-2726c7f26c'

You will have to set the same nonce on the [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style) element:

    <style nonce="2726c7f26c">
      #inline-style { background: red; }
    </style>

Alternatively, you can create hashes from your inline styles. CSP supports sha256, sha384 and sha512. The **binary** form of the hash has to be encoded with base64. You can obtain the hash of a string on the command line via the `openssl` program:

    echo -n "#inline-style { background: red; }" | openssl dgst -sha256 -binary | openssl enc -base64

You can use a hash-source to only allow specific inline style blocks:

    Content-Security-Policy: style-src 'sha256-ozBpjL6dxO8fsS4u6fwG1dFDACYvpNxYeBA6tzR+FY8='

When generating the hash, don't include the [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style) tags and note that capitalization and whitespace matter, including leading or trailing whitespace.

    <style>#inline-style { background: red; }</style>

### Unsafe style expressions

The `'unsafe-eval'` source expression controls several style methods that create style declarations from strings. If `'unsafe-eval'` isn't specified with the `style-src` directive, the following methods are blocked and won't have any effect:

-   [`CSSStyleSheet.insertRule()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/insertRule)
-   [`CSSGroupingRule.insertRule()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSGroupingRule/insertRule)
-   [`CSSStyleDeclaration.cssText`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/cssText)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-csp/#directive-style-src">Content Security Policy Level 3<br />
<span class="small">The definition of 'style-src' in that specification.</span></a></td><td><span class="spec-WD">Working Draft</span></td><td>No changes.</td></tr><tr class="even"><td><a href="https://w3c.github.io/webappsec-csp/2/#directive-style-src">Content Security Policy Level 2<br />
<span class="small">The definition of 'style-src' in that specification.</span></a></td><td><span class="spec-REC">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`style-src`

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

`style-src`

Yes

Yes

23

?

7

Yes

See also
--------

-   [`Content-Security-Policy`](../content-security-policy)
-   [`style-src-elem`](style-src-elem)
-   [`style-src-attr`](style-src-attr)
-   [`Link`](../link) header
-   [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style), [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link)
-   [`@import`](https://developer.mozilla.org/en-US/docs/Web/CSS/@import)
-   [`CSSStyleSheet.insertRule()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/insertRule)
-   [`CSSGroupingRule.insertRule()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSGroupingRule/insertRule)
-   [`CSSStyleDeclaration.cssText`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/cssText)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/style-src$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/style-src" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/style-src</a>
