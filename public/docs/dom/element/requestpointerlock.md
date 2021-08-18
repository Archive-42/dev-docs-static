Element.requestPointerLock()
============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Element.requestPointerLock()` method lets you asynchronously ask for the pointer to be locked on the given element.

To track the success or failure of the request, it is necessary to listen for the `pointerlockchange` and `pointerlockerror` events at the [`Document`](../document) level.

Syntax
------

    instanceOfElement.requestPointerLock();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/pointerlock/#dom-element-requestpointerlock">Pointer Lock<br />
<span class="small">The definition of 'requestPointerLock()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`requestPointerLock`

37

Yes

13

79

50

Yes

No

24

Yes

10.1

Yes

37

Yes

37

Yes

Yes

24

Yes

No

3.0

Yes

See also
--------

-   [`Document.pointerLockElement`](../document/pointerlockelement)
-   [`Document.exitPointerLock()`](../document/exitpointerlock)
-   [Pointer Lock](../pointer_lock_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/requestPointerLock" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/requestPointerLock</a>
