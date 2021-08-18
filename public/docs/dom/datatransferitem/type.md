# DataTransferItem.type

The read-only `DataTransferItem.type` property returns the type (format) of the [`DataTransferItem`](../datatransferitem) object representing the drag data item. The `type` is a Unicode string generally given by a MIME type, although a MIME type is not required.

Some example types are: `text/plain` and `text/html`.

## Syntax

    dataItem.type;

### Return value

A [`DOMString`](../domstring) representing the drag data item's type.

## Example

This example shows the use of the `type` property.

    function drop_handler(ev) {
     console.log("Drop");
     ev.preventDefault();
     var data = ev.dataTransfer.items;
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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#dom-datatransferitem-type">HTML Living Standard<br />
<span class="small">The definition of 'type' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial version</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/editing.html#dom-datatransferitem-type">HTML 5.1<br />
<span class="small">The definition of 'type' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of the HTML WHATWG document</td></tr></tbody></table>

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

`type`

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

- <span class="page-not-created">`DataTransfer.type()`</span>
- [Incomplete list of MIME types](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types/Common_types)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransferItem/type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransferItem/type</a>
