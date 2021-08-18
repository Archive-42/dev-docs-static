# Document: drag event

The `drag` event is fired every few hundred milliseconds as an element or text selection is being dragged by the user.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Default action</td><td>Continue the drag &amp; drop operation.</td></tr><tr class="even"><td>Interface</td><td><a href="../dragevent"><code>DragEvent</code></a></td></tr><tr class="odd"><td>Event handler property</td><td><a href="../globaleventhandlers/ondrag"><code>ondrag</code></a></td></tr></tbody></table>

## Examples

See this code in a [JSFiddle demo](https://jsfiddle.net/zfnj5rv4/) or interact with it below.

### HTML

    <div class="dropzone">
      <div id="draggable" draggable="true" ondragstart="event.dataTransfer.setData('text/plain',null)">
        This div is draggable
      </div>
    </div>
    <div class="dropzone"></div>
    <div class="dropzone"></div>
    <div class="dropzone"></div>

### CSS

    #draggable {
      width: 200px;
      height: 20px;
      text-align: center;
      background: white;
    }

    .dropzone {
      width: 200px;
      height: 20px;
      background: blueviolet;
      margin-bottom: 10px;
      padding: 10px;
    }

### JavaScript

    var dragged;

    /* events fired on the draggable target */
    document.addEventListener("drag", function(event) {

    }, false);

    document.addEventListener("dragstart", function(event) {
      // store a ref. on the dragged elem
      dragged = event.target;
      // make it half transparent
      event.target.style.opacity = .5;
    }, false);

    document.addEventListener("dragend", function(event) {
      // reset the transparency
      event.target.style.opacity = "";
    }, false);

    /* events fired on the drop targets */
    document.addEventListener("dragover", function(event) {
      // prevent default to allow drop
      event.preventDefault();
    }, false);

    document.addEventListener("dragenter", function(event) {
      // highlight potential drop target when the draggable element enters it
      if (event.target.className == "dropzone") {
        event.target.style.background = "purple";
      }

    }, false);

    document.addEventListener("dragleave", function(event) {
      // reset background of potential drop target when the draggable element leaves it
      if (event.target.className == "dropzone") {
        event.target.style.background = "";
      }

    }, false);

    document.addEventListener("drop", function(event) {
      // prevent default action (open as link for some elements)
      event.preventDefault();
      // move dragged elem to the selected drop target
      if (event.target.className == "dropzone") {
        event.target.style.background = "";
        dragged.parentNode.removeChild( dragged );
        event.target.appendChild( dragged );
      }
    }, false);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#dndevents">HTML Living Standard<br />
<span class="small">The definition of 'drag event' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`drag_event`

4

12

3.5

Firefox doesn't set the mouse coordinates during the drag event. See [bug 505521](https://bugzil.la/505521).

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
  - [`dragstart`](dragstart_event)
  - [`dragend`](dragend_event)
  - [`dragover`](dragover_event)
  - [`dragenter`](dragenter_event)
  - [`dragleave`](dragleave_event)
  - <span class="page-not-created">`dragexit`</span>
  - [`drop`](drop_event)
- This event on other targets:
  - [`Window`](../window): <span class="page-not-created">`drag`</span> event
  - [`HTMLElement`](../htmlelement): <span class="page-not-created">`drag`</span> event
  - [`SVGElement`](../svgelement): <span class="page-not-created">`drag`</span> event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/drag_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/drag_event</a>
