HID
===

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `HID` interface provides methods for connecting to *HID devices*, listing attached HID devices and event handlers for connected HID devices.

Properties
----------

*This interface also inherits properties of its parent, [`EventTarget`](eventtarget).*

### Event handlers

<span class="page-not-created">`HID.onconnect`</span>  
Fired when an HID device is connected.

<span class="page-not-created">`HID.ondisconnect`</span>  
Fired when an HID device is disconnected.

Methods
-------

*This interface also inherits methods of its parent, [`EventTarget`](eventtarget).*

<span class="page-not-created">`getDevices()`</span>  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an array of connected <span class="page-not-created">`HIDDevice`</span> objects.

<span class="page-not-created">`requestDevice()`</span>  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with an array of connected <span class="page-not-created">`HIDDevice`</span> objects from the HID device selected from popup.

You can only select one HID device from the popup at a time from this [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise), but the array might contain multiple <span class="page-not-created">`HIDDevice`</span>s.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webhid/#dom-hid">WebHID API<br />
<span class="small">The definition of 'HID' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`HID`

89

89

No

No

75

No

No

No

No

No

No

No

`getDevices`

89

89

No

No

75

No

No

No

No

No

No

No

`onconnect`

89

89

No

No

75

No

No

No

No

No

No

No

`ondisconnect`

89

89

No

No

75

No

No

No

No

No

No

No

`requestDevice`

89

89

No

No

75

No

No

No

No

No

No

No

See also
--------

-   [`WebHID API`](webhid_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HID" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HID</a>
