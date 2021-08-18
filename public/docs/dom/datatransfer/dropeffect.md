# DataTransfer.dropEffect

The `DataTransfer.dropEffect` property controls the feedback (typically visual) the user is given during a drag and drop operation. It will affect which cursor is displayed while dragging. For example, when the user hovers over a target drop element, the browser's cursor may indicate which type of operation will occur.

When the [`DataTransfer`](../datatransfer) object is created, `dropEffect` is set to a string value. On getting, it returns its current value. On setting, if the new value is one of the values listed below, then the property's current value will be set to the new value and other values will be ignored.

For the `dragenter` and `dragover` events, `dropEffect` will be initialized based on what action the user is requesting. How this is determined is platform specific, but typically the user can press modifier keys such as the alt key to adjust the desired action. Within event handlers for `dragenter` and `dragover` events, `dropEffect` should be modified if a different action is desired than the action that the user is requesting.

For the `drop` and `dragend` events, `dropEffect` will be set to the action that was desired, which will be the value `dropEffect` had after the last `dragenter` or `dragover` event. In a `dragend` event, for instance, if the desired dropEffect is "move", then the data being dragged should be removed from the source.

## Syntax

    dataTransfer.dropEffect;

### Values

A [`DOMString`](../domstring) representing the drag operation effect. The possible values are:

`copy`  
A copy of the source item is made at the new location.

`move`  
An item is moved to a new location.

`link`  
A link is established to the source at the new location.

`none`  
The item may not be dropped.

Assigning any other value to `dropEffect` has no effect and the old value is retained.

## Example

This example shows the use of the `dropEffect` and [`effectAllowed`](effectallowed) properties.

### HTML Content

    <div>
      <p id="source" ondragstart="dragstart_handler(event);" draggable="true">
        Select this element, drag it to the Drop Zone and then release the selection to move the element.
      </p>
    </div>
    <div id="target" ondrop="drop_handler(event);" ondragover="dragover_handler(event);">Drop Zone</div>

### CSS Content

    div {
      margin: 0em;
      padding: 2em;
    }

    #source {
      color: blue;
      border: 1px solid black;
    }

    #target {
      border: 1px solid black;
    }

### JavaScript Content

    function dragstart_handler(ev) {
      console.log("dragStart: dropEffect = " + ev.dataTransfer.dropEffect + " ; effectAllowed = " + ev.dataTransfer.effectAllowed);

      // Add this element's id to the drag payload so the drop handler will
      // know which element to add to its tree
      ev.dataTransfer.setData("text", ev.target.id);
      ev.dataTransfer.effectAllowed = "move";
    }

    function drop_handler(ev) {
      console.log("drop: dropEffect = " + ev.dataTransfer.dropEffect + " ; effectAllowed = " + ev.dataTransfer.effectAllowed);
      ev.preventDefault();

      // Get the id of the target and add the moved element to the target's DOM
      var data = ev.dataTransfer.getData("text");
      ev.target.appendChild(document.getElementById(data));
    }

    function dragover_handler(ev) {
      console.log("dragOver: dropEffect = " + ev.dataTransfer.dropEffect + " ; effectAllowed = " + ev.dataTransfer.effectAllowed);
      ev.preventDefault();
      // Set the dropEffect to move
      ev.dataTransfer.dropEffect = "move"
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#dom-datatransfer-dropeffect">HTML Living Standard<br />
<span class="small">The definition of 'dropEffect' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/editing.html#dom-datatransfer-dropeffect">HTML 5.1<br />
<span class="small">The definition of 'dropEffect' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`dropEffect`

Yes

12

3.5

?

Yes

Yes

Yes

Yes

4

Yes

No

Yes

## See also

- [Drag and drop](../html_drag_and_drop_api)
- [Drag Operations](../html_drag_and_drop_api/drag_operations)
- [Recommended Drag Types](../html_drag_and_drop_api/recommended_drag_types)
- [Dragging and Dropping Multiple Items](../html_drag_and_drop_api/multiple_items)
- [DataTransfer test - Paste or Drag](https://codepen.io/tech_query/pen/MqGgap)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/dropEffect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/dropEffect</a>
