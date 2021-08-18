Window.isSecureContext
======================

The `window.isSecureContext` read-only property indicates whether a context is capable of using features that require [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts).

Syntax
------

    var isSecure = window.isSecureContext

Examples
--------

### Feature detection

You can use feature detection to check whether they are in a secure context or not by using the `isSecureContext` boolean which is exposed on the global scope.

    if (window.isSecureContext) {
      // Page is a secure context so service workers are now available
      navigator.serviceWorker.register("/offline-worker.js").then(function () {
        ...
      });
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-secure-contexts/">Secure Contexts</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`isSecureContext`

47

15

49

No

34

11.1

47

47

49

34

11.3

5.0

`considers_window_opener`

No

No

49

No

?

?

No

No

49

?

?

No

See also
--------

-   [Secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/isSecureContext" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/isSecureContext</a>
