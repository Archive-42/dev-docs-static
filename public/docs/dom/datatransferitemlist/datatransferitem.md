# DataTransferItemList.DataTransferItem()

The `DataTransferItem()` getter method implements support for accessing items in the [`DataTransferItemList`](../datatransferitemlist) using array-style syntax (that is `DataTransferItem[index]`).

## Syntax

    dataItem = DataTransferItem[index];

### Parameters

`index`  
The zero-based index of the item in the drag data list to return.

### Return value

The [`DataTransferItem`](../datatransferitem) object at the specified index in the item list. If the index is less than zero or greater than or equal to the number of items in the list (as indicated by the list's [`length`](length) property, `undefined` is returned. The returned value is never `null`.

## Example

This example shows how to use drag and drop.

### JavaScript

    function dragstart_handler(ev) {
      console.log("dragStart");
      // Add this element's id to the drag payload so the drop handler will
      // know which element to add to its tree
      var dataList = ev.dataTransfer.items;
      dataList.add(ev.target.id, "text/plain");
      // Add some other items to the drag payload
      dataList.add("<p>... paragraph ...</p>", "text/html");
      dataList.add("http://www.example.org","text/uri-list");
    }

    function drop_handler(ev) {
      console.log("Drop");
      ev.preventDefault();
      var data = ev.dataTransfer.items;
      // Loop through the dropped items and log their data
      for (var i = 0; i < data.length; i++) {
        if ((data[i].kind == 'string') && (data[i].type.match('^text/plain'))) {
          // This item is the target node
          data[i].getAsString(function (s){
            ev.target.appendChild(document.getElementById(s));
          });
        } else if ((data[i].kind == 'string') && (data[i].type.match('^text/html'))) {
          // Drag data item is HTML
          data[i].getAsString(function (s){
            console.log("... Drop: HTML = " + s);
          });
        } else if ((data[i].kind == 'string') && (data[i].type.match('^text/uri-list'))) {
          // Drag data item is URI
          data[i].getAsString(function (s){
            console.log("... Drop: URI = " + s);
          });
        }
      }
    }

    function dragover_handler(ev) {
      console.log("dragOver");
      ev.preventDefault();
      // Set the dropEffect to move
      ev.dataTransfer.dropEffect = "move"
    }

    function dragend_handler(ev) {
      console.log("dragEnd");
      var dataList = ev.dataTransfer.items;
      // Clear any remaining drag data
      dataList.clear();
    }

### HTML

    <div>
      <p id="source" ondragstart="dragstart_handler(event);" ondragend="dragend_handler(event);" draggable="true">
         Select this element, drag it to the Drop Zone and then release the selection to move the element.</p>
    </div>
    <div id="target" ondrop="drop_handler(event);" ondragover="dragover_handler(event);">Drop Zone</div>

### CSS

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

### Result

[Drag and Drop demo link](https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Web/API/DataTransferItemList/DataTransferItem/_samples_/Example_Drag_and_Drop)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#the-datatransferitemlist-interface">HTML Living Standard<br />
<span class="small">The definition of 'DataTransferItem getter' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`DataTransferItem`

13

≤79

50

No

12

6

4.4

18

50

No

6

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransferItemList/DataTransferItem" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransferItemList/DataTransferItem</a>
