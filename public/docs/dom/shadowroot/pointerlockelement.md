ShadowRoot.pointerLockElement
=============================

The read-only `pointerLockElement` property of the [`ShadowRoot`](../shadowroot) interface provides the element set as the target for mouse events while the pointer is locked. It is `null` if lock is pending, pointer is unlocked, or the target is in another tree.

Syntax
------

    shadowRoot.pointerLockElement;

### Value

An [`Element`](../element) or `null`.

Examples
--------

    let customElem = document.querySelector('my-shadow-dom-element');
    let shadow = customElem.shadowRoot;
    let pleElem = shadow.pointerLockElement;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/pointerlock/#extensions-to-the-documentorshadowroot-mixin">Pointer Lock<br />
<span class="small">The definition of 'pointerLockElement' in that specification.</span></a></td></tr></tbody></table>

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

`pointerLockElement`

53

79

63

No

40

10.1

53

53

63

41

No

6.0

See also
--------

-   [`Document.exitPointerLock()`](../document/exitpointerlock)
-   [`Element.requestPointerLock()`](../element/requestpointerlock)
-   [Pointer Lock](../pointer_lock_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot/pointerLockElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot/pointerLockElement</a>
