# DragEvent

The `DragEvent` interface is a [`DOM event`](event) that represents a drag and drop interaction. The user initiates a drag by placing a pointer device (such as a mouse) on the touch surface and then dragging the pointer to a new location (such as another DOM element). Applications are free to interpret a drag and drop interaction in an application-specific way.

This interface inherits properties from [`MouseEvent`](mouseevent) and [`Event`](event).

## Properties

[`DragEvent.dataTransfer`](dragevent/datatransfer) <span class="badge inline readonly">Read only </span>  
The data that is transferred during a drag and drop interaction.

## Constructors

Although this interface has a constructor, it is not possible to create a useful DataTransfer object from script, since [`DataTransfer`](datatransfer) objects have a processing and security model that is coordinated by the browser during drag-and-drops.

[`DragEvent()`](dragevent/dragevent)  
Creates a synthetic and untrusted DragEvent.

## Event types

`drag`  
This event is fired when an element or text selection is being dragged.

`dragend`  
This event is fired when a drag operation is being ended (by releasing a mouse button or hitting the escape key).

`dragenter`  
This event is fired when a dragged element or text selection enters a valid drop target.

`dragexit`  
This event is fired when an element is no longer the drag operation's immediate selection target.

`dragleave`  
This event is fired when a dragged element or text selection leaves a valid drop target.

`dragover`  
This event is fired continuously when an element or text selection is being dragged and the mouse pointer is over a valid drop target (every 50 ms WHEN mouse is not moving ELSE much faster between 5 ms (slow movement) and 1ms (fast movement) approximately. This firing pattern is different than `mouseover` ).

`dragstart`  
This event is fired when the user starts dragging an element or text selection.

`drop`  
This event is fired when an element or text selection is dropped on a valid drop target.

## GlobalEventHandlers

[`GlobalEventHandlers.ondrag`](globaleventhandlers/ondrag)  
A [`global event handler`](globaleventhandlers) for the `drag` event.

[`GlobalEventHandlers.ondragend`](globaleventhandlers/ondragend)  
A [`global event handler`](globaleventhandlers) for the `dragend` event.

[`GlobalEventHandlers.ondragenter`](globaleventhandlers/ondragenter)  
A [`global event handler`](globaleventhandlers) for the `dragenter` event.

[`GlobalEventHandlers.ondragleave`](globaleventhandlers/ondragleave)  
A [`global event handler`](globaleventhandlers) for the `dragexit` event.

[`GlobalEventHandlers.ondragleave`](globaleventhandlers/ondragleave)  
A [`global event handler`](globaleventhandlers) for the `dragleave` event.

[`GlobalEventHandlers.ondragover`](globaleventhandlers/ondragover)  
A [`global event handler`](globaleventhandlers) for the `dragover` event.

[`GlobalEventHandlers.ondragstart`](globaleventhandlers/ondragstart)  
A [`global event handler`](globaleventhandlers) for the `dragstart` event.

[`GlobalEventHandlers.ondrop`](globaleventhandlers/ondrop)  
A [`global event handler`](globaleventhandlers) for the `drop` event.

## Example

An Example of each property, constructor, event type and global event handlers is included in their respective reference page.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dragevent">HTML Living Standard<br />
<span class="small">The definition of 'DragEvent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/editing.html#the-dragevent-interface">HTML 5.1<br />
<span class="small">The definition of 'DragEvent' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`DragEvent`

3

12

3.5

9

Before Internet Explorer 10, `DragEvent` is exposed in standards mode but not quirks mode.

12

3.1

No

No

4

No

No

No

`DragEvent`

46

12

3.5

No

12

3.1

No

No

Yes

No

No

No

`dataTransfer`

46

12

3.5

10

The value is always `null`.

Yes

3.1

No

No

Yes

No

No

No

## See also

- [Drag and drop](html_drag_and_drop_api)
- [Drag Operations](html_drag_and_drop_api/drag_operations)
- [Recommended Drag Types](html_drag_and_drop_api/recommended_drag_types)
- [Dragging and Dropping Multiple Items](html_drag_and_drop_api/multiple_items)
- [DataTransfer test - Paste or Drag](https://codepen.io/tech_query/pen/MqGgap)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DragEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DragEvent</a>
