# DataTransfer.setData()

The `DataTransfer.setData()` method sets the drag operation's [`drag data`](../datatransfer) to the specified data and type. If data for the given type does not exist, it is added at the end of the drag data store, such that the last item in the [`types`](types) list will be the new type. If data for the given type already exists, the existing data is replaced in the same position. That is, the order of the [`types`](types) list is not changed when replacing data of the same type.

Example data types are `text/plain` and `text/uri-list`.

## Syntax

    void dataTransfer.setData(format, data);

### Arguments

_format_  
A [`DOMString`](../domstring) representing the type of the drag data to add to the [`drag object`](../datatransfer).

_data_  
A [`DOMString`](../domstring) representing the data to add to the [`drag object`](../datatransfer).

### Return value

void

## Example

This example shows the use of the [`DataTransfer`](../datatransfer) object's [`getData()`](getdata), [`setData()`](setdata) and [`clearData()`](cleardata) methods.

    <!DOCTYPE html>
    <html lang=en>
    <title>Examples of DataTransfer's setData(), getData() and clearData()</title>
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
     console.log("dragStart");
     // Change the source element's background color to signify drag has started
     ev.currentTarget.style.border = "dashed";
     // Set the drag's format and data. Use the event target's id for the data
     ev.dataTransfer.setData("text/plain", ev.target.id);
    }

    function dragover_handler(ev) {
     console.log("dragOver");
     ev.preventDefault();
    }

    function drop_handler(ev) {
     console.log("Drop");
     ev.preventDefault();
     // Get the data, which is the id of the drop target
     var data = ev.dataTransfer.getData("text");
     ev.target.appendChild(document.getElementById(data));
     // Clear the drag data cache (for all formats/types)
     ev.dataTransfer.clearData();
    }
    </script>
    <body>
    <h1>Examples of <code>DataTransfer</code>: <code>setData()</code>, <code>getData()</code>, <code>clearData()</code></h1>
     <div>
       <p id="source" ondragstart="dragstart_handler(event);" draggable="true">
         Select this element, drag it to the Drop Zone and then release the selection to move the element.</p>
     </div>
     <div id="target" ondrop="drop_handler(event);" ondragover="dragover_handler(event);">Drop Zone</div>
    </body>
    </html>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#dom-datatransfer-setdata">HTML Living Standard<br />
<span class="small">The definition of 'setData()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/editing.html#dom-datatransfer-setdata">HTML 5.1<br />
<span class="small">The definition of 'setData()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`setData`

3

12

10

No

12

5

≤37

18

10

12

5

1.0

## See also

- [Drag and drop](../html_drag_and_drop_api)
- [Drag Operations](../html_drag_and_drop_api/drag_operations)
- [Recommended Drag Types](../html_drag_and_drop_api/recommended_drag_types)
- [Dragging and Dropping Multiple Items](../html_drag_and_drop_api/multiple_items)
- [DataTransfer test - Paste or Drag](https://codepen.io/tech_query/pen/MqGgap)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/setData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/setData</a>
