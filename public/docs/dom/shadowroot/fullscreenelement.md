ShadowRoot.fullscreenElement
============================

The `fullscreenElement` read-only property of the [`ShadowRoot`](../shadowroot) interface returns the element within the shadow tree that is currently displayed in full screen.

Syntax
------

    shadowRoot.fullscreenElement

### Value

The [`Element`](../element) which is currently is displayed in full screen mode, or `null` if there is no full screen element.

Examples
--------

    let customElem = document.querySelector('my-shadow-dom-element');
    let shadow = customElem.shadowRoot;
    let fullscreenElem = shadow.fullscreenElement;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-documentorshadowroot-fullscreenelement">HTML Living Standard<br />
<span class="small">The definition of 'fullscreenElement' in that specification.</span></a></td></tr></tbody></table>

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

`fullscreenElement`

71

79

64

63

No

58

No

71

71

64

63

50

No

10.0

See also
--------

-   [`Document.fullscreenElement`](../document/fullscreenelement)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot/fullscreenElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot/fullscreenElement</a>
