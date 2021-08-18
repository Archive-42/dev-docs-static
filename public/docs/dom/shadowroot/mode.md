ShadowRoot.mode
===============

The `mode` property of the [`ShadowRoot`](../shadowroot) specifies its mode — either `open` or `closed`. This defines whether or not the shadow root's internal features are accessible from JavaScript.

When the `mode` of a shadow root is "`closed`", the shadow root’s implementation internals are inaccessible and unchangeable from JavaScript—in the same way the implementation internals of, for example, the [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element are inaccessible and unchangeable from JavaScript.

Syntax
------

    var mode = shadowRoot.mode

### Value

A value defined in the `ShadowRootMode` enum — either `open` or `closed`.

Examples
--------

    let customElem = document.querySelector('my-shadow-dom-element');
    let shadow = customElem.shadowRoot;

    // Another way to check whether the shadow root is open; it will return null if not
    if(shadow) {
      // If it is open, close it to stop people stealing our secrets!
      shadow.mode = 'closed';
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-shadowroot-mode">DOM<br />
<span class="small">The definition of 'ShadowRoot.mode' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`mode`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot/mode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot/mode</a>
