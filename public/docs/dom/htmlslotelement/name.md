HTMLSlotElement.name
====================

The `name` property of the [`HTMLSlotElement`](../htmlslotelement) interface returns or sets the slot name. A slot is a placeholder inside a web component that users can fill with their own markup.

Syntax
------

    var name = htmlSlotElement.name
    htmlSlotElement.name = name

### Value

A [`DOMString`](../domstring).

Examples
--------

The following snippet is taken from our [slotchange example](https://github.com/mdn/web-components-examples/tree/master/slotchange) ([see it live also](https://mdn.github.io/web-components-examples/slotchange/)).

    let slots = this.shadowRoot.querySelectorAll('slot');
    slots[1].addEventListener('slotchange', function(e) {
      let nodes = slots[1].assignedNodes();
      console.log('Element in Slot "' + slots[1].name + '" changed to "' + nodes[0].outerHTML + '".');
    });

Here we grab references to all the slots, then add a slotchange event listener to the 2nd slot in the template — which is the one that keeps having its contents changed in the example.

Every time the element inserted in the slot changes, we log a report to the console saying which slot has changed, and what the new node inside the slot is.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-slot-name">HTML Living Standard<br />
<span class="small">The definition of 'name' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`name`

53

79

63

No

40

10

53

53

63

41

10

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSlotElement/name" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLSlotElement/name</a>
