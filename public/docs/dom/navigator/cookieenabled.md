Navigator.cookieEnabled
=======================

`navigator.cookieEnabled` returns a Boolean value that indicates whether cookies are enabled or not. The property is read-only.

Syntax
------

    var cookieEnabled = navigator.cookieEnabled;

-   `cookieEnabled` is a [Boolean](https://developer.mozilla.org/en-US/docs/Glossary/Boolean): `true` or `false`.

**Note:** When the browser is configured to block third-party cookies, and `navigator.cookieEnabled` is invoked inside a third-party iframe, it returns `true` in Safari, Edge Spartan and IE (while trying to set a cookie in such scenario would fail). It returns `false` in Firefox and Chromium-based browsers.

**Note:** Web browsers may prevent writing certain cookies in certain scenarios. For example, Chrome 80+ does not allow creating cookies with `SameSite=None` attribute, [unless they are created over HTTPS and with `Secure` attribute.](https://www.chromestatus.com/feature/5633521622188032)

Example
-------

    if (!navigator.cookieEnabled) {
      // The browser does not support or is blocking cookies from being set.
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#dom-navigator-cookieenabled">HTML Living Standard<br />
<span class="small">The definition of 'Navigator.cookieEnabled' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`cookieEnabled`

1

12

1

Prior to Firefox 8, `navigator.cookieEnabled` would report the wrong result if a site exception was in place for the page on which the check was performed. This has been fixed.

4

`navigator.cookieEnabled` returns `true even if the browser is set to block cookies (for example, if the page is in the Restricted sites security zone).`

≤12.1

1

1

18

4

Prior to Firefox 8, `navigator.cookieEnabled` would report the wrong result if a site exception was in place for the page on which the check was performed. This has been fixed.

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/cookieEnabled" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/cookieEnabled</a>
