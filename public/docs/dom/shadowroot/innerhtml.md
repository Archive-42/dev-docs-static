ShadowRoot.innerHTML
====================

The `innerHTML` property of the [`ShadowRoot`](../shadowroot) interface sets or returns a reference to the DOM tree inside the `ShadowRoot`.

Syntax
------

    var domString = shadowRoot.innerHTML
    shadowRoot.innerHTML = domString

### Value

A [`DOMString`](../domstring).

Examples
--------

    let customElem = document.querySelector('my-shadow-dom-element');
    let shadow = customElem.shadowRoot;

    shadow.innerHTML = '<strong>This element should be more important!</strong>';

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/DOM-Parsing/#dom-innerhtml-innerhtml">DOM Parsing and Serialization<br />
<span class="small">The definition of 'ShadowRoot.innerHTML' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`innerHTML`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot/innerHTML" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot/innerHTML</a>
