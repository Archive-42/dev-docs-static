# DataTransfer.types

The `DataTransfer.types` read-only property returns an array of the drag data formats (as [`strings`](../domstring)) that were set in the `dragstart` event. The order of the formats is the same order as the data included in the drag operation.

The formats are Unicode strings giving the type or format of the data, generally given by a MIME type. Some values that are not MIME types are special-cased for legacy reasons (for example "`text`").

## Syntax

    dataTransfer.types;

### Return value

An array of the data formats used in the drag operation. Each format is [`string`](../domstring). If the drag operation included no data, this list will be empty. If any files are included in the drag operation, then one of the types will be the string `Files`.

## Example

This example shows the use of the `types` and [`items`](items) properties.

    <!DOCTYPE html>
    <html lang=en>
    <title>Examples of DataTransfer.{types,items} properties</title>
    <meta content="width=device-width">
    <style>
      div {
        margin: 0em;
        padding: 2em;
      }
      #target {
        border: 1px solid black;
      }
    </style>
    <script>
    function dragstart_handler(ev) {
     console.log("dragStart: target.id = " + ev.target.id);
     // Add this element's id to the drag payload so the drop handler will
     // know which element to add to its tree
     ev.dataTransfer.setData("text/plain", ev.target.id);
     ev.dataTransfer.effectAllowed = "move";
    }

    function drop_handler(ev) {
     console.log("drop: target.id = " + ev.target.id);
     ev.preventDefault();
     // Get the id of the target and add the moved element to the target's DOM
     var data = ev.dataTransfer.getData("text");
     ev.target.appendChild(document.getElementById(data));
     // Print each format type
     if (ev.dataTransfer.types != null) {
       for (var i=0; i < ev.dataTransfer.types.length; i++) {
         console.log("... types[" + i + "] = " + ev.dataTransfer.types[i]);
       }
     }
     // Print each item's "kind" and "type"
     if (ev.dataTransfer.items != null) {
       for (var i=0; i < ev.dataTransfer.items.length; i++) {
         console.log("... items[" + i + "].kind = " + ev.dataTransfer.items[i].kind + " ; type = " + ev.dataTransfer.items[i].type);
       }
     }
    }

    function dragover_handler(ev) {
     console.log("dragOver");
     ev.preventDefault();
     // Set the dropEffect to move
     ev.dataTransfer.dropEffect = "move"
    }
    </script>
    <body>
    <h1>Examples of <code>DataTransfer</code>.{<code>types</code>, <code>items</code>} properties</h1>
     <ul>
       <li id="i1" ondragstart="dragstart_handler(event);" draggable="true">Drag Item 1 to the Drop Zone</li>
       <li id="i2" ondragstart="dragstart_handler(event);" draggable="true">Drag Item 2 to the Drop Zone</li>
     </ul>
     <div id="target" ondrop="drop_handler(event);" ondragover="dragover_handler(event);">Drop Zone</div>
    </body>
    </html>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#dom-datatransfer-types">HTML Living Standard<br />
<span class="small">The definition of 'types' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/editing.html#dom-datatransfer-types">HTML 5.1<br />
<span class="small">The definition of 'types' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`types`

Yes

12

3.5

10

\["The property returns a [`DOMStringList`](https://developer.mozilla.org/docs/Web/API/DOMStringList).", "`Text` is returned instead of `text/plain`"\]

Yes

As of Opera 12, `Text` is returned instead of `text/plain`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/types" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/types</a>
