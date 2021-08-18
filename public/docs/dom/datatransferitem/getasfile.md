# DataTransferItem.getAsFile()

If the item is a file, the `DataTransferItem.getAsFile()` method returns the drag data item's [`File`](../file) object. If the item is not a file, this method returns `null`.

## Syntax

    File = DataTransferItem.getAsFile();

### Parameters

_None._

### Return value

[`File`](../file)  
If the drag data item is a file, a [`File`](../file) object is returned; otherwise `null` is returned.

## Example

This example shows the use of the `getAsFile()` method in a `drop` event handler.

    function drop_handler(ev) {
     console.log("Drop");
     ev.preventDefault();
     var data = event.dataTransfer.items;
     for (var i = 0; i < data.length; i += 1) {
       if ((data[i].kind == 'string') &&
           (data[i].type.match('^text/plain'))) {
         // This item is the target node
         data[i].getAsString(function (s){
           ev.target.appendChild(document.getElementById(s));
         });
       } else if ((data[i].kind == 'string') &&
                  (data[i].type.match('^text/html'))) {
         // Drag data item is HTML
         console.log("... Drop: HTML");
       } else if ((data[i].kind == 'string') &&
                  (data[i].type.match('^text/uri-list'))) {
         // Drag data item is URI
         console.log("... Drop: URI");
       } else if ((data[i].kind == 'file') &&
                  (data[i].type.match('^image/'))) {
         // Drag data item is an image file
         var f = data[i].getAsFile();
         console.log("... Drop: File ");
       }
     }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#dom-datatransferitem-getasfile">HTML Living Standard<br />
<span class="small">The definition of 'getAsFile()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial value</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/editing.html#dom-datatransferitem-getasfile">HTML 5.1<br />
<span class="small">The definition of 'getAsFile()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of the HTML WHATWG document</td></tr></tbody></table>

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

`getAsFile`

11

12

50

No

12

5.1

4

18

50

No

5

1.0

## See also

- [`DataTransfer.files`](../datatransfer/files)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransferItem/getAsFile" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransferItem/getAsFile</a>
