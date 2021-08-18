# DataTransfer.getData()

The `DataTransfer.getData()` method retrieves drag data (as a [`DOMString`](../domstring)) for the specified type. If the drag operation does not include data, this method returns an empty string.

Example data types are `text/plain` and `text/uri-list`.

## Syntax

    dataTransfer.getData(format);

### Arguments

`format`  
A [`DOMString`](../domstring) representing the type of data to retrieve.

### Return value

[`DOMString`](../domstring)  
A [`DOMString`](../domstring) representing the drag data for the specified `format`. If the drag operation has no data or the operation has no data for the specified `format`, this method returns an empty string.

### Caveats

Data availability  
The [HTML5 Drag and Drop Specification](https://www.w3.org/TR/2011/WD-html5-20110113/dnd.html#drag-data-store-mode) dictates a `drag data store mode`. This may result in unexpected behavior, being `DataTransfer.getData()` not returning an expected value.

## Example

This example shows the use of the [`DataTransfer`](../datatransfer) object's [`getData()`](getdata) and [`setData()`](setdata) methods.

### HTML Content

    <div id="div1" ondrop="drop(event)" ondragover="allowDrop(event)">
        <span id="drag" draggable="true" ondragstart="drag(event)">drag me to the other box</span>
    </div>
    <div id="div2" ondrop="drop(event)" ondragover="allowDrop(event)"></div>

### CSS Content

    #div1, #div2 {
        width:100px;
        height:50px;
        padding:10px;
        border:1px solid #aaaaaa;
    }

### JavaScript Content

    function allowDrop(allowdropevent) {
        allowdropevent.target.style.color = 'blue';
        allowdropevent.preventDefault();
    }

    function drag(dragevent) {
        dragevent.dataTransfer.setData("text", dragevent.target.id);
        dragevent.target.style.color = 'green';
    }

    function drop(dropevent) {
        dropevent.preventDefault();
        var data = dropevent.dataTransfer.getData("text");
        dropevent.target.appendChild(document.getElementById(data));
        document.getElementById("drag").style.color = 'black';
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#dom-datatransfer-getdata">HTML Living Standard<br />
<span class="small">The definition of 'getData()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/editing.html#dom-datatransfer-getdata">HTML 5.1<br />
<span class="small">The definition of 'getData()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`getData`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/getData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer/getData</a>
