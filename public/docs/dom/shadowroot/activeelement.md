ShadowRoot.activeElement
========================

The `activeElement` read-only property of the [`ShadowRoot`](../shadowroot) interface returns the element within the shadow tree that has focus.

Syntax
------

    shadowRoot.activeElement

### Value

The [`Element`](../element) which currently has focus, or `null` if there is no focused element.

Examples
--------

    let customElem = document.querySelector('my-shadow-dom-element');
    let shadow = customElem.shadowRoot;
    let focusedElem = shadow.activeElement;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-documentorshadowroot-activeelement">HTML Living Standard<br />
<span class="small">The definition of 'activeElement' in that specification.</span></a></td></tr></tbody></table>

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

`activeElement`

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

10.3

6.0

See also
--------

-   [`Document.activeElement`](../document/activeelement)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot/activeElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot/activeElement</a>
