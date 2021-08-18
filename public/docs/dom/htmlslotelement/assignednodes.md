# HTMLSlotElement.assignedNodes()

The `assignedNodes()` property of the [`HTMLSlotElement`](../htmlslotelement) interface returns a sequence of the nodes assigned to this slot, and if the `flatten` option is set to `true`, the assigned nodes of any other slots that are descendants of this slot. If no assigned nodes are found, it returns the slot's fallback content.

## Syntax

    var assignedNodes = HTMLSlotElement.assignedNodes(options)

### Parameters

options <span class="badge inline optional">Optional</span>  
An object that sets options for the nodes to be returned. The available options are:

- `flatten`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether to return the assigned nodes of any available child `<slot>` elements (`true`) or not (`false`). Defaults to `false`.

### Return value

An array of nodes.

## Examples

The following snippet is taken from our [slotchange example](https://github.com/mdn/web-components-examples/tree/master/slotchange) ([see it live also](https://mdn.github.io/web-components-examples/slotchange/)).

    let slots = this.shadowRoot.querySelectorAll('slot');
    slots[1].addEventListener('slotchange', function(e) {
      let nodes = slots[1].assignedNodes();
      console.log('Element in Slot "' + slots[1].name + '" changed to "' + nodes[0].outerHTML + '".');
    });

Here we grab references to all the slots, then add a slotchange event listener to the 2nd slot in the template — which is the one that keeps having its contents changed in the example.

Every time the element inserted in the slot changes, we log a report to the console saying which slot has changed, and what the new node inside the slot is.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-slot-assignednodes">HTML Living Standard<br />
<span class="small">The definition of 'assignedNodes' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

## Browser compatibility

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSlotElement/assignedNodes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLSlotElement/assignedNodes</a>
