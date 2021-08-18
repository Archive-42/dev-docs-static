# DataTransferItem.kind

The read-only `DataTransferItem.kind` property returns a [`DataTransferItem`](../datatransferitem) representing the _drag data item_ kind: some text or some file.

## Syntax

    var itemKind = DataTransferItem.kind;

### Return value

A [`DOMString`](../domstring) representing the drag data item's kind. It must be one of the following values:

`'file'`  
If the drag data item is a file.

`'string'`  
If the kind of drag data item is a _plain Unicode string_.

## Example

This example shows the use of the `kind` property.

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
       } else if ((data[i].kind == 'file') &&
                  (data[i].type.match('^image/'))) {
         // Drag data item is an image file
         var f = data[i].getAsFile();
         console.log("... Drop: File ");
       }
     }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#dom-datatransferitem-kind">HTML Living Standard<br />
<span class="small">The definition of 'kind' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial version</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/editing.html#dom-datatransferitem-kind">HTML 5.1<br />
<span class="small">The definition of 'kind' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>W3C snapshot of the WHATWG document.</td></tr></tbody></table>

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

`kind`

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

- [Drag and drop](../html_drag_and_drop_api)
- [Drag Operations](../html_drag_and_drop_api/drag_operations)
- [Recommended Drag Types](../html_drag_and_drop_api/recommended_drag_types)
- [Dragging and Dropping Multiple Items](../html_drag_and_drop_api/multiple_items)
- [DataTransfer test - Paste or Drag](https://codepen.io/tech_query/pen/MqGgap)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransferItem/kind" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransferItem/kind</a>
