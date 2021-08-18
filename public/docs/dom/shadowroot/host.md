ShadowRoot.host
===============

The `host` read-only property of the [`ShadowRoot`](../shadowroot) returns a reference to the DOM element the `ShadowRoot` is attached to.

Syntax
------

    const someElement = shadowRoot.host

### Value

A DOM [`Element`](../element).

Examples
--------

    let customElem = document.querySelector('my-shadow-dom-element');
    let shadow = customElem.shadowRoot;

      ...

    // return the original host element some time later
    let hostElem = shadow.host;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-shadowroot-host">DOM<br />
<span class="small">The definition of 'ShadowRoot.host' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`host`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot/host" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot/host</a>
