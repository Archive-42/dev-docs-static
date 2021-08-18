# Document: dragenter event

The `dragenter` event is fired when a dragged element or text selection enters a valid drop target.

The target object is the _immediate user selection_ (the element directly indicated by the user as the drop target), or the [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body) element.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Default action</td><td>Reject immediate user selection as potential target element.</td></tr><tr class="even"><td>Interface</td><td><a href="../dragevent"><code>DragEvent</code></a></td></tr><tr class="odd"><td>Event handler property</td><td><a href="../globaleventhandlers/ondragenter"><code>ondragenter</code></a></td></tr></tbody></table>

## Examples

See the [drag event](drag_event) for example code or this [JSFiddle demo](https://jsfiddle.net/zfnj5rv4/).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#dndevents">HTML Living Standard<br />
<span class="small">The definition of 'dragenter' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`dragenter_event`

4

12

3.5

In Firefox, the `dragenter` event is fired twice when the dropzone is parent of draggable or draggable itself. See [bug 804036](https://bugzil.la/804036) for details.

10

12

3.1

No

No

No

No

11

No

## See also

- Other drag and drop events:
  - [`drag`](drag_event)
  - [`dragstart`](dragstart_event)
  - [`dragend`](dragend_event)
  - [`dragover`](dragover_event)
  - [`dragleave`](dragleave_event)
  - <span class="page-not-created">`dragexit`</span>
  - [`drop`](drop_event)
- This event on other targets:
  - [`Window`](../window): <span class="page-not-created">`dragenter`</span> event
  - [`HTMLElement`](../htmlelement): <span class="page-not-created">`dragenter`</span> event
  - [`SVGElement`](../svgelement): <span class="page-not-created">`dragenter`</span> event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/dragenter_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/dragenter_event</a>
