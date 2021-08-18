XRInputSource.profiles
======================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The read-only [`XRInputSource`](../xrinputsource) property `profiles` returns an array of strings, each describing a configuration profile for the input source. The profile strings are listed in order of specificity, with the most specific profile listed first.

**Note:** The `profiles` list is always empty when the WebXR session is in inline mode.

Syntax
------

    let profileList = xrInputSource.profiles;

### Value

An array of [`DOMString`](../domstring) objects, each describing one configuration profile for the input device represented by the `XRInputSource` object. Each input profile specifies the preferred visual representation and behavior of the input source.

Usage notes
-----------

### Input profile names

An input profile name is a string describing a visual representation and behavior the input source may be configured to use. Each string:

-   Has no spaces; instead, words are separated by hyphen ("-") characters
-   If the platform makes it available, the USB vendor and product ID may be provided but cannot be relied upon
-   Does not uniquely identify a specific device; rather, it identifies a configuration that the product is capable of using
-   Does not provide information about handedness of the device, if applicable

The [WebXR Input Profiles Registry](https://github.com/immersive-web/webxr-input-profiles/tree/master/packages/registry) is used by device developers and browser developers to attempt to ensure that a given device will report the same profile strings regardless of which browser or other [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) you use.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrinputsource-profiles">WebXR Device API<br />
<span class="small">The definition of 'XRInputSource.profiles' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`profiles`

79

79

No

No

No

No

No

79

No

No

No

11.2

See also
--------

-   [WebXR Device API](../webxr_device_api)
-   [Inputs and input sources](../webxr_device_api/inputs)
-   [Using gamepads in WebXR applications](https://developer.mozilla.org/en-US/docs/Web/WebXR%20Device%20API/Gamepads)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRInputSource/profiles" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRInputSource/profiles</a>
