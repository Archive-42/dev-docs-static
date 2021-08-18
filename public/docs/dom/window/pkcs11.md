Window.pkcs11
=============

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Summary
-------

Returns the `pkcs11` object, which is used to install drivers and other software associated with the [pkcs11 protocol](https://developer.mozilla.org/en-US/docs/Pkcs11_protocol). If `pkcs11` isn't supported, this property returns `null`.

**Note:** This property has been returned `null` since Gecko 1.9.0.14 (Firefox 3.0.14) and **removed** in Gecko 29.0 (Firefox 29 / Thunderbird 29 / SeaMonkey 2.26)) for security reasons. For more information on installing PKCS11 modules, see [installing PKCS11 modules](https://developer.mozilla.org/en-US/docs/PKCS11_Module_Installation). See [bug 326628](https://bugzilla.mozilla.org/show_bug.cgi?id=326628) for details on why the property was removed.

Syntax
------

    objRef = window.pkcs11

Example
-------

     window.pkcs11.addModule(sMod, secPath, 0, 0);

Notes
-----

See <span class="page-not-created">`nsIDOMPkcs11`</span> for more information about how to manipulate `pkcs11` objects.

Specifications
--------------

Not part of specification.

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

`pkcs11`

No

No

1-29

No

?

No

No

No

4-29

?

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/pkcs11" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/pkcs11</a>
