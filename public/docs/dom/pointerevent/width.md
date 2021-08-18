PointerEvent.width
==================

The `width` read-only property of the [`PointerEvent`](../pointerevent) interface represents the width of the pointer's contact geometry along the x-axis, measured in CSS pixels. Depending on the source of the pointer device (such as a finger), for a given pointer, each event may produce a different value.

If the input hardware cannot report the contact geometry to the browser, the width defaults to `1`.

Syntax
------

    var contactWidth = pointerEvent.width;

### Return value

`contactWidth`  
The width of the event's contact area (in CSS pixels).

Example
-------

This example illustrates using the [`PointerEvent`](../pointerevent) interface's [`width`](width) and [`height`](height) properties to calculate the contact area.

    target.addEventListener("pointerdown", function(ev) {
       // Calculate the contact area
       var area = ev.width * ev.height;
     }, false);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#dom-pointerevent-width">Pointer Events – Level 2<br />
<span class="small">The definition of 'width' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Non-stable version.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#widl-PointerEvent-width">Pointer Events<br />
<span class="small">The definition of 'width' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`width`

55

12

59

41

11

10

Returns values in screen pixels instead of CSS document pixels.

42

13

55

55

79

41

42

13

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent/width" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PointerEvent/width</a>
