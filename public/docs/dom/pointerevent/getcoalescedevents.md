PointerEvent.getCoalescedEvents()
=================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `getCoalescedEvents()` method of the [`PointerEvent`](../pointerevent) interface returns a sequence of all `PointerEvent` instances that were coalesced into the dispatched `pointermove` event.

Syntax
------

    var pointerEvents[] = PointerEvent.getCoalescedEvents()

### Parameters

None.

### Returns

A sequence of [`PointerEvent`](../pointerevent) instances.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/pointerevents/#dom-pointerevent-getcoalescedevents">Pointer Events – Level 3<br />
<span class="small">The definition of 'getCoalescedEvents()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getCoalescedEvents`

58

79

59

No

45

No

58

58

79

59

43

No

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent/getCoalescedEvents" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent/getCoalescedEvents</a>
