ShadowRoot.pictureInPictureElement
==================================

The `pictureInPictureElement` read-only property of the [`ShadowRoot`](../shadowroot) interface returns the [`Element`](../element) that is currently being presented in picture-in-picture mode in this shadow tree, or `null` if picture-in-picture mode is not currently in use.

Syntax
------

    shadowRoot.pictureInPictureElement

### Value

A reference to the [`Element`](../element) object that's currently in picture-in-picture mode, or, if picture-in-picture mode isn't currently in use by the shadow tree, the returned value is `null`.

Examples
--------

    let customElem = document.querySelector('my-shadow-dom-element');
    let shadow = customElem.shadowRoot;
    let pipElem = shadow.pictureInPictureElement;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/picture-in-picture/#dom-documentorshadowroot-pictureinpictureelement">Picture-in-Picture API<br />
<span class="small">The definition of 'pictureInPictureElement' in that specification.</span></a></td></tr></tbody></table>

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

`pictureInPictureElement`

69

79

No

No

56

13.1

No

No

No

No

13.4

No

See also
--------

-   [`Document.pictureInPictureElement`](../document/pictureinpictureelement)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot/pictureInPictureElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot/pictureInPictureElement</a>
