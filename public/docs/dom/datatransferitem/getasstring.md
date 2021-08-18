# DataTransferItem.getAsString()

The `DataTransferItem.getAsString()` method invokes the given callback with the drag data item's string data as the argument if the item's [`kind`](kind) is a _Plain unicode string_ (i.e. `kind` is `string`).

## Syntax

    dataTransferItem.getAsString(callback);

### Parameters

`callback`  
A callback function that has access to the [`data transfer item's`](../datatransferitem) string data. See [Callback](#callback) below for details.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

## Callback

The callback parameter is a callback function which accepts one parameter:

[`DOMString`](../domstring)  
The drag data item's string data.

The callback return value is `undefined`.

## Example

This example shows the use of the `getAsString()` method as an _inline function_ in a `drop` event handler.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#dom-datatransferitem-getasstring">HTML Living Standard<br />
<span class="small">The definition of 'getAsString()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/editing.html#dom-datatransferitem-getasstring">HTML 5.1<br />
<span class="small">The definition of 'getAsString()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot fo HTML WHATWG document</td></tr></tbody></table>

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

`getAsString`

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

- [`DataTransfer.getData()`](../datatransfer/getdata)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransferItem/getAsString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransferItem/getAsString</a>
