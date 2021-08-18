DOMTokenList.supports()
=======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `supports()` method of the [`DOMTokenList`](../domtokenlist) interface returns `true` if a given `token` is in the associated attribute's supported tokens. This method is intended to support feature detection.

Syntax
------

    let trueOrFalse = element.supports(token)

### Parameters

`token`  
A [`DOMString`](../domstring) containing the token to query for.

### Returns

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the token was found.

Example
-------

    let iframe = document.getElementById('display');

    if (iframe.sandbox.supports('an-upcoming-feature')) {
      // support code for mystery future feature
    } else {
      // fallback code
    }

    if (iframe.sandbox.supports('allow-scripts')) {
      // instruct frame to run JavaScript
      //
      // (NOTE: This feature is well-supported; this is just an example!)
      //
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-credential-management/">Credential Management Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`supports`

49

17

49

No

36

10.1

49

49

49

36

10.3

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/supports" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/supports</a>
