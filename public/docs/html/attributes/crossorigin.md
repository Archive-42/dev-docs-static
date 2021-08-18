HTML attribute: crossorigin
===========================

**Draft**

This page is not complete.

The crossorigin attribute, valid on the [`<audio>`](../element/audio), [`<img>`](../element/img), [`<link>`](../element/link), [`<script>`](../element/script), and [`<video>`](../element/video) elements, provides support for [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS), defining how the element handles crossorigin requests, thereby enabling the configuration of the CORS requests for the element's fetched data. Depending on the element, the attribute can be a CORS settings attribute.

The `crossorigin` content attribute on media elements is a CORS settings attribute.

These attributes are enumerated, and have the following possible values:

<table><thead><tr class="header"><th>Keyword</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>anonymous</code></td><td>CORS requests for this element will have the credentials flag set to 'same-origin'.</td></tr><tr class="even"><td><code>use-credentials</code></td><td>CORS requests for this element will have the credentials flag set to 'include'.</td></tr><tr class="odd"><td><code>""</code></td><td>Setting the attribute name to an empty value, like <code>crossorigin</code> or <code>crossorigin=""</code>, is the same as <code>anonymous</code>.</td></tr></tbody></table>

By default (that is, when the attribute is not specified), CORS is not used at all. The "anonymous" keyword means that there will be no exchange of **user credentials** via cookies, client-side SSL certificates or HTTP authentication as described in the [Terminology section of the CORS specification](https://www.w3.org/TR/cors/#user-credentials), unless it is in the same origin.

An invalid keyword and an empty string will be handled as the `anonymous` keyword.

Prior to Firefox 83 the `crossorigin` attribute was not supported for `rel="icon"` there is also [an open issue for Chrome](https://bugs.chromium.org/p/chromium/issues/detail?id=1121645).

### Example: crossorigin with the script element

You can use the following [`<script>`](../element/script) element to tell a browser to execute the `https://example.com/example-framework.js` script without sending user-credentials.

    <script src="https://example.com/example-framework.js" crossorigin="anonymous"></script>

### Example: Webmanifest with credentials

The `use-credentials` value must be used when fetching a [manifest](https://developer.mozilla.org/en-US/docs/Web/Manifest) that requires credentials, even if the file is from the same origin.

    <link rel="manifest" href="/app.webmanifest" crossorigin="use-credentials">

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/infrastructure.html#cors-settings-attributes">HTML Living Standard<br />
<span class="small">The definition of 'CORS settings attributes' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/embedded-content.html#attr-img-crossorigin">HTML Living Standard<br />
<span class="small">The definition of 'crossorigin' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`crossorigin`

25

79

18

Before Firefox 83, `crossorigin` is not supported for `rel="icon"`.

No

15

?

37

Yes

18

?

?

Yes

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

`crossorigin`

?

≤18

74

12-74

With `crossorigin="use-credentials"`, cookies aren't sent during seek. See [bug 1532722](https://bugzil.la/1532722).

?

?

?

?

?

79

14-79

With `crossorigin="use-credentials"`, cookies aren't sent during seek. See [bug 1532722](https://bugzil.la/1532722).

?

?

?

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

BCD tables only load in the browser

### video crossorigin

BCD tables only load in the browser

### link crossorigin

BCD tables only load in the browser

See also
--------

-   [Cross-Origin Resource Sharing (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
-   [HTML attribute: `rel`](rel)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/crossorigin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/crossorigin</a>
