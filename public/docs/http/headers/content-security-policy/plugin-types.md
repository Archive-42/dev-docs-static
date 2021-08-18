CSP: plugin-types
=================

The HTTP [`Content-Security-Policy`](../content-security-policy) (CSP) `plugin-types` directive restricts the set of plugins that can be embedded into a document by limiting the types of resources which can be loaded.

Instantiation of an [`<embed>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed), [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object) or [`<applet>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/applet) element will fail if:

-   the element to load does not declare a valid MIME type,
-   the declared type does not match one of specified types in the `plugin-types` directive,
-   the fetched resource does not match the declared type.

<table><tbody><tr class="odd"><td>CSP version</td><td>2</td></tr><tr class="even"><td>Directive type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Document_directive">Document directive</a></td></tr><tr class="odd"><td><a href="default-src"><code>default-src</code></a> fallback</td><td>No. Not setting this allows anything.</td></tr></tbody></table>

Syntax
------

One or more [MIME types](../../basics_of_http/mime_types) can be set for the `plugin-types` policy:

    Content-Security-Policy: plugin-types <type>/<subtype>;
    Content-Security-Policy: plugin-types <type>/<subtype> <type>/<subtype>;

&lt;type&gt;/&lt;subtype&gt;  
A valid [MIME type](../../basics_of_http/mime_types/complete_list_of_mime_types).

Examples
--------

### Disallowing plugins

To disallow all plugins, the [`object-src`](object-src) directive should be set to `'none'` which will disallow plugins. The `plugin-types` directive is only used if you are allowing plugins with `object-src` at all.

    <meta http-equiv="Content-Security-Policy" content="object-src 'none'">

### Allowing Flash content

The content security policy

    Content-Security-Policy: plugin-types application/x-shockwave-flash

will allow to load flash objects:

    <object data="https://example.com/flash" type="application/x-shockwave-flash"></object>

### Allowing Java applets

To load an [`<applet>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/applet) you must specify `application/x-java-applet`:

    Content-Security-Policy: plugin-types application/x-java-applet

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-csp/#directive-plugin-types">Content Security Policy Level 3<br />
<span class="small">The definition of 'plugin-types' in that specification.</span></a></td><td><span class="spec-WD">Working Draft</span></td><td>No changes.</td></tr><tr class="even"><td><a href="https://w3c.github.io/webappsec-csp/2/#directive-plugin-types">Content Security Policy Level 2<br />
<span class="small">The definition of 'plugin-types' in that specification.</span></a></td><td><span class="spec-REC">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`plugin-types`

40

15

No

 No   
See [bug 1045899](https://bugzil.la/1045899).

No

27

10

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`plugin-types`

Yes

Yes

No

?

9.3

Yes

See also
--------

-   [`Content-Security-Policy`](../content-security-policy): [`object-src`](object-src)
-   [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object)
-   [`<embed>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed)
-   [`<applet>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/applet)
-   [`X-Content-Type-Options`](../x-content-type-options)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/plugin-types$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/plugin-types" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/plugin-types</a>
