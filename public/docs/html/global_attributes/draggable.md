draggable
=========

The **draggable** [global attribute](../global_attributes) is an enumerated attribute that indicates whether the element can be dragged, either with native browser behavior or the [HTML Drag and Drop API](https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API).

`draggable` can have the following values:

-   `true`: the element can be dragged.
-   `false`: the element cannot be dragged.

This attribute is *enumerated* and not *Boolean*. A value of `true` or `false` is mandatory, and shorthand like `<img draggable>` is forbidden. The correct usage is `<img draggable="false">`.

If this attribute is not set, its default value is `auto`, which means drag behavior is the default browser behavior: only text selections, images, and links can be dragged. For other elements, the event [`ondragstart`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ondragstart) must be set for drag and drop to work, as shown in this [comprehensive example](https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API/Drag_operations).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#the-draggable-attribute">HTML Living Standard<br />
<span class="small">The definition of 'draggable' in that specification.</span></a></td></tr></tbody></table>

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

`draggable`

Yes

12

2

Yes

12

Yes

Yes

Yes

4

Yes

Yes

Yes

See also
--------

-   All [global attributes](../global_attributes).

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/draggable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/draggable</a>
