HTMLElement.inert
=================

The [`HTMLElement`](../htmlelement) property `inert` is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that, when present, makes the browser "ignore" user input events for the element, including focus events and events from assistive technologies. The browser may also ignore page search and text selection in the element. This can be useful when building UIs such as modals where you would want to "trap" the focus inside the modal when it's visible.

Syntax
------

    isInert = HTMLElement.inert;

    HTMLElement.inert = true | false;

### Value

A Boolean which is `true` if the element is inert; otherwise, the value is `false`.

Example
-------

### HTML

    <div>
      <label for="button1">Button 1</label>
      <button id="button1">I am not inert</button>
    </div>
    <div inert>
      <label for="button2">Button 2</label>
      <button id="button2">I am inert</button>
    </div>

### CSS

    [inert] > * {
      opacity: .5;
    }

Note that the attribute, by itself, will not cause any visual change to the content as displayed in the browser. In the example above, CSS has been applied so that any direct descendant of an element with the inert attribute is rendered semi-opaque.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#inert-subtrees">HTML Living Standard<br />
<span class="small">The definition of 'HTMLElement.inert' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`inert`

60

79

81

No

47

No

No

60

81

44

No

No

See also
--------

-   [Inert Polyfill](https://github.com/WICG/inert)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/inert" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/inert</a>
