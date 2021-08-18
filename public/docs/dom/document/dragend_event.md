# Document: dragend event

The `dragend` event is fired when a drag operation is being ended (by releasing a mouse button or hitting the escape key).

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Default action</td><td>Varies</td></tr><tr class="even"><td>Interface</td><td><a href="../dragevent"><code>DragEvent</code></a></td></tr><tr class="odd"><td>Event handler property</td><td><a href="../globaleventhandlers/ondragend"><code>ondragend</code></a></td></tr></tbody></table>

## Examples

See the [drag](drag_event) event for example code or this [JSFiddle demo](https://jsfiddle.net/zfnj5rv4/).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#dndevents">HTML Living Standard<br />
<span class="small">The definition of 'dragend' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`dragend_event`

4

Prior to Chrome 72, the `dragend` event was not dispatched if an iframe (not necessarily the source target) is involved in a DOM operation. See [issue 737691](https://crbug.com/737691) for more details.

12

3.5

\["Firefox doesn't set the mouse coordinates during the drag event. See [bug 505521](https://bugzil.la/505521).", "In Firefox, `dragend` is not dispatched if the source node is moved or removed during the drag (e.g. on `drop` or `dragover`). See [bug 460801](https://bugzil.la/460801) for details."\]

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
  - [`dragover`](dragover_event)
  - [`dragenter`](dragenter_event)
  - [`dragleave`](dragleave_event)
  - <span class="page-not-created">`dragexit`</span>
  - [`drop`](drop_event)
- This event on other targets:
  - [`Window`](../window): <span class="page-not-created">`dragend`</span> event
  - [`HTMLElement`](../htmlelement): <span class="page-not-created">`dragend`</span> event
  - [`SVGElement`](../svgelement): <span class="page-not-created">`dragend`</span> event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/dragend_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/dragend_event</a>
