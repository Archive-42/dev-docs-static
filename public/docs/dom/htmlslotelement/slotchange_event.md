# HTMLSlotElement: slotchange event

The `slotchange` event is fired on an [`HTMLSlotElement`](../htmlslotelement) instance ([`<slot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/slot) element) when the node(s) contained in that slot change.

**Note:** the `slotchange` event doesn't fire if the children of a slotted node change — only if you change (e.g. add or delete) the actual nodes themselves.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td>None</td></tr></tbody></table>

In order to trigger a **slotchange** event, one has to set or remove the `slot `attribute.

## Examples

    element.setAttribute('slot', slotName);
    // element.assignedSlot = $slot
    element.removeAttribute('slot');
    // element.assignedSlot = null

The following snippet is taken from our [slotchange example](https://github.com/mdn/web-components-examples/tree/master/slotchange) ([see it live also](https://mdn.github.io/web-components-examples/slotchange/)).

    let slots = this.shadowRoot.querySelectorAll('slot');
    slots[1].addEventListener('slotchange', function(e) {
      let nodes = slots[1].assignedNodes();
      console.log('Element in Slot "' + slots[1].name + '" changed to "' + nodes[0].outerHTML + '".');
    });

Here we grab references to all the `<slot>`s, then add a `slotchange` event listener to the template's second slot — which is the one which has its contents changed in the example.

Every time the element inserted in the slot changes, we log a report to the console saying which slot has changed, and what the new node inside the slot is.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#mutation-observers">DOM<br />
<span class="small">The definition of '"Mutation observers" and slotchange event' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

## See also

[`HTMLSlotElement`](../htmlslotelement)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSlotElement/slotchange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLSlotElement/slotchange_event</a>
