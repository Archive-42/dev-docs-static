&lt;script&gt;: The Script element
==================================

The `<script>` is used to embed executable code or data; this is typically used to embed or refer to JavaScript code. The `<script>` element can also be used with other languages, such as [WebGL](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API)'s GLSL shader programming language and [JSON](https://developer.mozilla.org/en-US/docs/Glossary/JSON).

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#metadata_content">Metadata content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="even"><td>Permitted content</td><td>Dynamic script such as <code>text/javascript</code>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#metadata_content">metadata content</a>, or any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLScriptElement"><code>HTMLScriptElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

`async`  
For classic scripts, if the `async` attribute is present, then the classic script will be fetched in parallel to parsing and evaluated as soon as it is available.

For [module scripts](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules), if the `async` attribute is present then the scripts and all their dependencies will be executed in the defer queue, therefore they will get fetched in parallel to parsing and evaluated as soon as they are available.

This attribute allows the elimination of **parser-blocking JavaScript** where the browser would have to load and evaluate scripts before continuing to parse. `defer` has a similar effect in this case.

This is a boolean attribute: the presence of a boolean attribute on an element represents the true value, and the absence of the attribute represents the false value.

See [Browser compatibility](#browser_compatibility) for notes on browser support. See also [Async scripts for asm.js](https://developer.mozilla.org/en-US/docs/Games/Techniques/Async_scripts).

`crossorigin`  
Normal `script` elements pass minimal information to the [`window.onerror`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onerror) for scripts which do not pass the standard [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS) checks. To allow error logging for sites which use a separate domain for static media, use this attribute. See [CORS settings attributes](../attributes/crossorigin) for a more descriptive explanation of its valid arguments.

`defer`  
This Boolean attribute is set to indicate to a browser that the script is meant to be executed after the document has been parsed, but before firing `DOMContentLoaded`.

Scripts with the `defer` attribute will prevent the `DOMContentLoaded` event from firing until the script has loaded and finished evaluating.

This attribute must not be used if the `src` attribute is absent (i.e. for inline scripts), in this case it would have no effect.

The `defer` attribute has no effect on [module scripts](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules) — they defer by default.

Scripts with the `defer` attribute will execute in the order in which they appear in the document.

This attribute allows the elimination of **parser-blocking JavaScript** where the browser would have to load and evaluate scripts before continuing to parse. `async` has a similar effect in this case.

`integrity`  
This attribute contains inline metadata that a user agent can use to verify that a fetched resource has been delivered free of unexpected manipulation. See [Subresource Integrity](https://developer.mozilla.org/en-US/docs/Web/Security/Subresource_Integrity).

`nomodule`  
This Boolean attribute is set to indicate that the script should not be executed in browsers that support [ES2015 modules](https://hacks.mozilla.org/2015/08/es6-in-depth-modules/) — in effect, this can be used to serve fallback scripts to older browsers that do not support modular JavaScript code.

`nonce`  
A cryptographic nonce (number used once) to whitelist scripts in a [script-src Content-Security-Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/script-src). The server must generate a unique nonce value each time it transmits a policy. It is critical to provide a nonce that cannot be guessed as bypassing a resource's policy is otherwise trivial.

`referrerpolicy`  
Indicates which [referrer](https://developer.mozilla.org/en-US/docs/Web/API/Document/referrer) to send when fetching the script, or resources fetched by the script:

-   `no-referrer`: The [`Referer`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer) header will not be sent.
-   `no-referrer-when-downgrade` (default): The [`Referer`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer) header will not be sent to [origin](https://developer.mozilla.org/en-US/docs/Glossary/Origin)s without [TLS](https://developer.mozilla.org/en-US/docs/Glossary/TLS) ([HTTPS](https://developer.mozilla.org/en-US/docs/Glossary/https)).
-   `origin`: The sent referrer will be limited to the origin of the referring page: its [scheme](https://developer.mozilla.org/en-US/docs/Glossary/Protocol), [host](https://developer.mozilla.org/en-US/docs/Glossary/Host), and [port](https://developer.mozilla.org/en-US/docs/Glossary/Port).
-   `origin-when-cross-origin`: The referrer sent to other origins will be limited to the scheme, the host, and the port. Navigations on the same origin will still include the path.
-   `same-origin`: A referrer will be sent for [same origin](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy), but cross-origin requests will contain no referrer information.
-   `strict-origin`: Only send the origin of the document as the referrer when the protocol security level stays the same (e.g. HTTPS→HTTPS), but don't send it to a less secure destination (e.g. HTTPS→HTTP).
-   `strict-origin-when-cross-origin`: Send a full URL when performing a same-origin request, but only send the origin when the protocol security level stays the same (e.g.HTTPS→HTTPS), and send no header to a less secure destination (e.g. HTTPS→HTTP).
-   `unsafe-url`: The referrer will include the origin *and* the path (but not the [fragment](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/hash), [password](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/password), or [username](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/username)). **This value is unsafe**, because it leaks origins and paths from TLS-protected resources to insecure origins.

**Note**: An empty string value (`""`) is both the default value, and a fallback value if `referrerpolicy` is not supported. If `referrerpolicy` is not explicitly specified on the `<script>` element, it will adopt a higher-level referrer policy, i.e. one set on the whole document or domain. If a higher-level policy is not available, the empty string is treated as being equivalent to `no-referrer-when-downgrade`.

`src`  
This attribute specifies the URI of an external script; this can be used as an alternative to embedding a script directly within a document.

`type`  
This attribute indicates the type of script represented. The value of this attribute will be in one of the following categories:

-   **Omitted or a JavaScript MIME type:** This indicates the script is JavaScript. The HTML5 specification urges authors to omit the attribute rather than provide a redundant MIME type. In earlier browsers, this identified the scripting language of the embedded or imported (via the `src` attribute) code. JavaScript MIME types are [listed in the specification](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types#javascript_types).
-   `module` Causes the code to be treated as a JavaScript module. The processing of the script contents is not affected by the `charset` and `defer` attributes. For information on using `module`, see our [JavaScript modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules) guide. Unlike classic scripts, module scripts require the use of the CORS protocol for cross-origin fetching.
-   **Any other value:** The embedded content is treated as a data block which won't be processed by the browser. Developers must use a valid MIME type that is not a JavaScript MIME type to denote data blocks. The `src` attribute will be ignored.

### Deprecated attributes

 `charset` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
If present, its value must be an ASCII case-insensitive match for "`utf-8`". It’s unnecessary to specify the `charset` attribute, because documents must use UTF-8, and the `script` element inherits its character encoding from the document.

 `language` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Like the `type` attribute, this attribute identifies the scripting language in use. Unlike the `type` attribute, however, this attribute’s possible values were never standardized. The `type` attribute should be used instead.

Notes
-----

Scripts without [`async`](#attr-async) , [`defer`](#attr-defer) or `type="module"` attributes, as well as inline scripts, are fetched and executed immediately, before the browser continues to parse the page.

The script should be served with the `text/javascript` MIME type, but browsers are lenient and only block them if the script is served with an image type (`image/*`); a video type (`video/*`); an audio (`audio/*`) type; or `text/csv`. If the script is blocked, an `error` is sent to the element, if not a `load` event is sent.

Examples
--------

### Basic usage

These examples show how to import (an external) script using the `<script>` element.

    <script src="javascript.js"></script>

And the following examples show how to put (an inline) script inside the `<script>` element.

    <script>
      alert("Hello World!");
    </script>

### Module fallback

Browsers that support the `module` value for the [`type`](#attr-type) attribute ignore any script with a `nomodule` attribute. That enables you to use module scripts while also providing `nomodule`-marked fallback scripts for non-supporting browsers.

    <script type="module" src="main.js"></script>
    <script nomodule src="fallback.js"></script>

### Embedding data in HTML

You can also use the `<script>` element to embed data in HTML with server-side rendering by specifying a valid non-JavaScript MIME type in the `type` attribute.

    <!-- Generated by the server -->
    <script id="data" type="application/json">{"userId":1234,"userName":"John Doe","memberSince":"2000-01-01T00:00:00.000Z"}</script>

    <!-- Static -->
    <script>
      const userInfo = JSON.parse(document.getElementById("data").text);
      console.log("User information: %o", userInfo);
    </script>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comments</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#the-script-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;script&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Removed the <a href="#attr-charset"><code>charset</code></a> attribute</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/semantics-scripting.html#the-script-element">HTML5<br />
<span class="small">The definition of '&lt;script&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/interact/scripts.html#h-18.2.1">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;script&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`script`

1

12

1

Starting in Firefox 4, inserting &lt;script&gt; elements that have been created by calling `document.createElement("script")` no longer enforces execution in insertion order. This change lets Firefox properly abide by the specification. To make script-inserted external scripts execute in their insertion order, set `.async=false` on them.

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`async`

1

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`crossorigin`

30

≤18

13

No

12

Yes

The `crossorigin` attribute was implemented in WebKit in WebKit [bug 81438](https://webkit.org/b/81438).

Yes

Yes

14

?

?

Yes

`defer`

Yes

Chrome does not defer scripts with the `defer` attribute when the page is served as XHTML (`application/xhtml+xml`) - [Chromium Issue \#611136](https://crbug.com/611136), [Chromium Issue \#874749](https://crbug.com/874749)

12

3.5

Since Firefox 3.6, the `defer` attribute is ignored on scripts that don't have the `src` attribute. However, in Firefox 3.5 even inline scripts are deferred if the `defer` attribute is set.

10

In versions prior to Internet Explorer 10, it implemented `defer` by a proprietary specification. Since version 10 it conforms to the W3C specification.

Yes

Opera does not defer scripts with the `defer` attribute when the page is served as XHTML (`application/xhtml+xml`) - [Chromium Issue \#611136](https://crbug.com/611136), [Chromium Issue \#874749](https://crbug.com/874749)

Yes

Yes

WebView does not defer scripts with the `defer` attribute when the page is served as XHTML (`application/xhtml+xml`) - [Chromium Issue \#611136](https://crbug.com/611136), [Chromium Issue \#874749](https://crbug.com/874749)

Yes

Chrome does not defer scripts with the `defer` attribute when the page is served as XHTML (`application/xhtml+xml`) - [Chromium Issue \#611136](https://crbug.com/611136), [Chromium Issue \#874749](https://crbug.com/874749)

4

Yes

Opera does not defer scripts with the `defer` attribute when the page is served as XHTML (`application/xhtml+xml`) - [Chromium Issue \#611136](https://crbug.com/611136), [Chromium Issue \#874749](https://crbug.com/874749)

Yes

Yes

Samsung Internet does not defer scripts with the `defer` attribute when the page is served as XHTML (`application/xhtml+xml`) - [Chromium Issue \#611136](https://crbug.com/611136), [Chromium Issue \#874749](https://crbug.com/874749)

`integrity`

45

17

43

No

Yes

11.1

45

45

43

?

11.3

5.0

`language`

1

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`nomodule`

61

16

60

No

48

11

61

61

60

45

11

8.0

`referrerpolicy`

70

≤79

65

No

Yes

No

70

70

65

?

No

10.0

`src`

1

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`text`

1

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`type`

1

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

### Compatibility notes

In older browsers that don't support the `async` attribute, parser-inserted scripts block the parser; script-inserted scripts execute asynchronously in IE and WebKit, but synchronously in Opera and pre-4 Firefox. In Firefox 4, the `async` DOM property defaults to `true` for script-created scripts, so the default behavior matches the behavior of IE and WebKit.

To request script-inserted external scripts be executed in the insertion order in browsers where the `document.createElement("script").async` evaluates to `true` (such as Firefox 4), set `async="false"` on the scripts you want to maintain order.

Never call `document.write()` from an async script. In Firefox 3.6, calling `document.write()` has an unpredictable effect. In Firefox 4, calling `document.write()` from an async script has no effect (other than printing a warning to the error console).

See also
--------

-   [`document.currentScript`](https://developer.mozilla.org/en-US/docs/Web/API/Document/currentScript)
-   [Ryan Grove's `<script>` and `<link>` node event compatibility chart](https://pie.gd/test/script-link-events/)
-   [Flavio Copes' article on loading JavaScript efficiently and explaining the differences between `async` and `defer`](https://flaviocopes.com/javascript-async-defer/)
-   [JavaScript modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules) guide

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script</a>
