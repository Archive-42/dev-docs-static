# DataTransfer.items

The read-only [`DataTransfer`](../datatransfer) property `items` property is a [`list`](../datatransferitemlist) of the [`data transfer items`](../datatransferitem) in a drag operation. The list includes one item for each item in the operation and if the operation had no items, the list is empty.

## Syntax

    itemList = dataTransfer.items;

### Return value

A [`DataTransferItemList`](../datatransferitemlist) object containing [`DataTransferItem`](../datatransferitem) objects representing the items being dragged in a drag operation, one list item for each object being dragged. If the drag operation had no data, the list is empty.

## Example

This example shows the use of the `items` and [`types`](types) properties.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#dom-datatransfer-items">HTML Living Standard<br />
<span class="small">The definition of 'items' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/editing.html#dom-datatransfer-items">HTML 5.1<br />
<span class="small">The definition of 'items' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`items`

4

12

50

No

12

11.1

Yes

Yes

52

Yes

11.3

Yes

## See also

- [Drag and drop](../html_drag_and_drop_api)
- [Drag Operations](../html_drag_and_drop_api/drag_operations)
- [Recommended Drag Types](../html_drag_and_drop_api/recommended_drag_types)
- [Dragging and Dropping Multiple Items](../html_drag_and_drop_api/multiple_items)
- [DataTransfer test - Paste or Drag](https://codepen.io/tech_query/pen/MqGgap)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/items" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/items</a>
