Element: assignedSlot
=====================

The `assignedSlot` read-only property of the [`Element`](../element) interface returns an [`HTMLSlotElement`](../htmlslotelement) representing the [`<slot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/slot) element the node is inserted in.

Syntax
------

    var slotElement = elementInstance.assignedSlot

### Value

An [`HTMLSlotElement`](../htmlslotelement) instance, or `null` if the element is not assigned to a slot, or if the associated shadow root was attached with its [`mode`](../shadowroot/mode) set to `closed` (see [`Element.attachShadow`](attachshadow) for further details).

Examples
--------

In our [simple-template example](https://github.com/mdn/web-components-examples/tree/master/simple-template) ([see it live](https://mdn.github.io/web-components-examples/simple-template/)), we create a trivial custom element example called `<my-paragraph>` in which a shadow root is attached and then populated using the contents of a template that contains a slot named `my-text`.

When `<my-paragraph>` is used in the document, the slot is populated by a slottable element by including it inside the element with a `slot` attribute with the value `my-text`. Here is one such example:

    <my-paragraph>
      <span slot="my-text">Let's have some different text!</span>
    </my-paragraph>

In our JavaScript file we get a reference to the [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) shown above, then log a reference to the original `<slot>` element the `<span>` was inserted in.

    let slottedSpan = document.querySelector('my-paragraph span')
    console.log(slottedSpan.assignedSlot); // logs '<slot name="my-text">'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-slotable-assignedslot">DOM<br />
<span class="small">The definition of 'assignedSlot' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`assignedSlot`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/assignedSlot" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/assignedSlot</a>
