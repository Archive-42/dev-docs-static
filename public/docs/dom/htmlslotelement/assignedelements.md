HTMLSlotElement.assignedElements()
==================================

The `assignedElements()` property of the [`HTMLSlotElement`](../htmlslotelement) interface returns a sequence of the elements assigned to this slot (and no other nodes). If the `flatten` option is set to `true`, it also returns the assigned elements of any other slots that are descendants of this slot. If no assigned nodes are found, it returns the slot's fallback content.

Syntax
------

    var assignedElements = HTMLSlotElement.assignedElements(options)

### Parameters

 options <span class="badge inline optional">Optional</span>   
An object that sets options for the nodes to be returned. The available options are:

-   `flatten`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether to return the assigned elements of any available child `<slot>` elements (`true`) or not (`false`). Defaults to `false`.

### Return value

An array of elements.

Examples
--------

    let slots = this.shadowRoot.querySelector('slot');
    let elements = slots.assignedElements({flatten: true});

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-slot-assignedelements">HTML Living Standard<br />
<span class="small">The definition of 'assignedElements()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSlotElement/assignedElements" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLSlotElement/assignedElements</a>
