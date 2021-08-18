# DataTransfer.effectAllowed

The `DataTransfer.effectAllowed` property specifies the effect that is allowed for a drag operation. The _copy_ operation is used to indicate that the data being dragged will be copied from its present location to the drop location. The _move_ operation is used to indicate that the data being dragged will be moved, and the _link_ operation is used to indicate that some form of relationship or connection will be created between the source and drop locations.

This property should be set in the `dragstart` event to set the desired drag effect for the drag source. Within the `dragenter` and `dragover` event handlers, this property will be set to whatever value was assigned during the `dragstart` event, thus `effectAllowed` may be used to determine which effect is permitted.

Assigning a value to `effectAllowed` in events other than `dragstart` has no effect.

## Syntax

    dataTransfer.effectAllowed;

### Values

A [`DOMString`](../domstring) representing the drag operation that is allowed. The possible values are:

none  
The item may not be dropped.

copy  
A copy of the source item may be made at the new location.

copyLink  
A copy or link operation is permitted.

copyMove  
A copy or move operation is permitted.

link  
A link may be established to the source at the new location.

linkMove  
A link or move operation is permitted.

move  
An item may be moved to a new location.

all  
All operations are permitted.

uninitialized  
The default value when the effect has not been set, equivalent to all.

Assigning any other value to `effectAllowed` has no effect and the old value is retained.

Internet Explorer will change the value to be lowercased; thus, `linkMove` will become `linkmove`, and so on.

## Example

This example shows the use of the `effectAllowed` and [`dropEffect`](dropeffect) properties.

    <!DOCTYPE html>
    <html lang=en>
    <title>Examples of DataTransfer.{dropEffect,effectAllowed} properties</title>
    <meta content="width=device-width">
    <style>
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
    </style>
    <script>
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
    </script>
    <body>
    <h1>Examples <code>DataTransfer</code>.{<code>dropEffect</code>, <code>effectAllowed</code>} properties</h1>
     <div>
       <p id="source" ondragstart="dragstart_handler(event);" draggable="true">
         Select this element, drag it to the Drop Zone and then release the selection to move the element.</p>
     </div>
     <div id="target" ondrop="drop_handler(event);" ondragover="dragover_handler(event);">Drop Zone</div>
    </body>
    </html>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#dom-datatransfer-effectallowed">HTML Living Standard<br />
<span class="small">The definition of 'effectAllowed' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/editing.html#dom-datatransfer-effectallowed">HTML 5.1<br />
<span class="small">The definition of 'effectAllowed' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`effectAllowed`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/effectAllowed" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/effectAllowed</a>
