HTMLSlotElement
===============

The `HTMLSlotElement` interface of the [Shadow DOM API](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM) enables access to the name and assigned nodes of an HTML [`<slot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/slot) element.

Properties
----------

[`HTMLSlotElement.name`](htmlslotelement/name)  
[`DOMString`](domstring): Can be used to get and set the slot's name.

Methods
-------

[`HTMLSlotElement.assignedNodes()`](htmlslotelement/assignednodes)  
Returns a sequence of the nodes assigned to this slot, and if the `flatten` option is set to `true`, the assigned nodes of any other slots that are descendants of this slot. If no assigned nodes are found, it returns the slot's fallback content.

[`HTMLSlotElement.assignedElements()`](htmlslotelement/assignedelements)  
Returns a sequence of the elements assigned to this slot (and no other nodes). If the `flatten` option is set to `true`, it also returns the assigned elements of any other slots that are descendants of this slot. If no assigned nodes are found, it returns the slot's fallback content.

Events
------

[`slotchange`](htmlslotelement/slotchange_event)  
Fired on an `HTMLSlotElement` instance ([`<slot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/slot) element) when the node(s) contained in that slot change.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#htmlslotelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLSlotElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`HTMLSlotElement`

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

`assignedElements`

65

79

66

No

52

12.1

65

65

66

47

12.2

9.0

`assignedNodes`

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

`slotchange_event`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSlotElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLSlotElement</a>
