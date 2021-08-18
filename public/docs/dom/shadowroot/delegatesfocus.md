ShadowRoot.delegatesFocus
=========================

The `delegatesFocus` read-only property of the [`ShadowRoot`](../shadowroot) interface returns a boolean that indicates whether delegatesFocus was set when the shadow was attached (see [`Element.attachShadow()`](../element/attachshadow)).

Syntax
------

    var df = shadowRoot.delegatesFocus

### Value

A boolean value — `true` if the shadow root does delegate focus, `false` if it doesn't.

Examples
--------

    let customElem = document.querySelector('my-shadow-dom-element');
    let shadow = customElem.shadowRoot;

      ...

    // Does it delegate focus?
    let hostElem = shadow.delegatesFocus;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-shadowroot-delegatesfocus">DOM<br />
<span class="small">The definition of 'delegatesFocus' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`delegatesFocus`

53

79

?

No

40

No

53

53

?

41

No

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot/delegatesFocus" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot/delegatesFocus</a>
