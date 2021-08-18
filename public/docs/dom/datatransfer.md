# DataTransfer

The `DataTransfer` object is used to hold the data that is being dragged during a drag and drop operation. It may hold one or more data items, each of one or more data types. For more information about drag and drop, see [HTML Drag and Drop API](html_drag_and_drop_api).

This object is available from the [`dataTransfer`](dragevent/datatransfer) property of all [`drag events`](dragevent).

## Constructor

[`DataTransfer()`](datatransfer/datatransfer)  
Creates and returns a new `DataTransfer` object.

## Properties

### Standard properties

[`DataTransfer.dropEffect`](datatransfer/dropeffect)  
Gets the type of drag-and-drop operation currently selected or sets the operation to a new type. The value must be `none`, `copy`, `link` or `move`.

[`DataTransfer.effectAllowed`](datatransfer/effectallowed)  
Provides all of the types of operations that are possible. Must be one of `none`, `copy`, `copyLink`, `copyMove`, `link`, `linkMove`, `move`, `all` or `uninitialized`.

[`DataTransfer.files`](datatransfer/files)  
Contains a list of all the local files available on the data transfer. If the drag operation doesn't involve dragging files, this property is an empty list.

[`DataTransfer.items`](datatransfer/items) <span class="badge inline readonly">Read only </span>  
Gives a [`DataTransferItemList`](datatransferitemlist) object which is a list of all of the drag data.

[`DataTransfer.types`](datatransfer/types) <span class="badge inline readonly">Read only </span>  
An array of [`strings`](domstring) giving the formats that were set in the `dragstart` event.

### Gecko properties

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Note:** All of the properties in this section are Gecko-specific.

[`DataTransfer.mozCursor`](datatransfer/mozcursor)  
Gives the drag cursor's state. This is primarily used to control the cursor during tab drags.

[`DataTransfer.mozSourceNode`](datatransfer/mozsourcenode) <span class="badge inline readonly">Read only </span>  
The [`Node`](node) over which the mouse cursor was located when the button was pressed to initiate the drag operation. This value is `null` for external drags or if the caller can't access the node.

[`DataTransfer.mozUserCancelled`](datatransfer/mozusercancelled) <span class="badge inline readonly">Read only </span>  
This property applies only to the `dragend` event, and is `true` if the user canceled the drag operation by pressing escape. It will be `false` in all other cases, including if the drag failed for any other reason, for instance due to a drop over an invalid location.

### Deprecated properties

[`DataTransfer.mozItemCount`](datatransfer/mozitemcount) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Gives the number of items in the drag operation. Removed in Firefox 71.

## Methods

### Standard methods

[`DataTransfer.clearData()`](datatransfer/cleardata)  
Remove the data associated with a given type. The type argument is optional. If the type is empty or not specified, the data associated with all types is removed. If data for the specified type does not exist, or the data transfer contains no data, this method will have no effect.

[`DataTransfer.getData()`](datatransfer/getdata)  
Retrieves the data for a given type, or an empty string if data for that type does not exist or the data transfer contains no data.

[`DataTransfer.setData()`](datatransfer/setdata)  
Set the data for a given type. If data for the type does not exist, it is added at the end, such that the last item in the types list will be the new format. If data for the type already exists, the existing data is replaced in the same position.

[`DataTransfer.setDragImage()`](datatransfer/setdragimage)  
Set the image to be used for dragging if a custom one is desired.

### Gecko methods

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Note:** All of the methods in this section are Gecko-specific.

[`DataTransfer.addElement()`](datatransfer/addelement)  
Sets the drag source to the given element.

### Deprecated methods

[`DataTransfer.mozClearDataAt()`](datatransfer/mozcleardataat) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Removes the data associated with the given format for an item at the specified index. The index is in the range from zero to the number of items minus one. Removed in Firefox 71.

[`DataTransfer.mozGetDataAt()`](datatransfer/mozgetdataat) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Retrieves the data associated with the given format for an item at the specified index, or null if it does not exist. The index should be in the range from zero to the number of items minus one. Removed in Firefox 71.

[`DataTransfer.mozSetDataAt()`](datatransfer/mozsetdataat) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A data transfer may store multiple items, each at a given zero-based index. `mozSetDataAt()` may only be called with an index argument less than `mozItemCount` in which case an existing item is modified, or equal to `mozItemCount` in which case a new item is added, and the `mozItemCount` is incremented by one. Removed in Firefox 71.

[`DataTransfer.mozTypesAt()`](datatransfer/moztypesat) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Holds a list of the format types of the data that is stored for an item at the specified index. If the index is not in the range from 0 to the number of items minus one, an empty string list is returned. Removed in Firefox 71.

## Examples

Every method and property listed in this document has its own reference page and each reference page either directly includes an example of the interface or has a link to an example.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#datatransfer">HTML Living Standard<br />
<span class="small">The definition of 'DataTransfer' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td><code>mozCursor</code>, <code>mozItemCount</code>, <code>mozSourceNode</code>, <code>mozUserCancelled</code>, <code>addElement()</code>, <code>mozClearDataAt()</code>, <code>mozGetDataAt()</code>, <code>mozSetDataAt()</code> and <code>mozTypesAt</code> are Gecko specific.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/editing.html#the-datatransfer-interface">HTML 5.1<br />
<span class="small">The definition of 'DataTransfer' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Not included in W3C HTML5 <span class="spec-rec">Recommendation</span></td></tr></tbody></table>

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

`DataTransfer`

3

12

3.5

As of Firefox 52, the [`DataTransfer.types`](https://developer.mozilla.org/docs/Web/API/DataTransfer/types) property returns a frozen array of [`DOMString`](https://developer.mozilla.org/docs/Web/API/DOMString)s as per spec, rather than a [`DOMStringList`](https://developer.mozilla.org/docs/Web/API/DOMStringList).

10

12

3.1

≤37

18

4

As of Firefox 52, the [`DataTransfer.types`](https://developer.mozilla.org/docs/Web/API/DataTransfer/types) property returns a frozen array of [`DOMString`](https://developer.mozilla.org/docs/Web/API/DOMString)s as per spec, rather than a [`DOMStringList`](https://developer.mozilla.org/docs/Web/API/DOMStringList).

12

2

1.0

`DataTransfer`

60

17

62

No

47

14.1

60

60

62

44

14.5

8.0

`addElement`

No

No

3.5

No

No

No

No

No

4

No

No

No

`clearData`

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

`dropEffect`

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

`files`

Yes

12

3.6

?

Yes

Yes

Yes

Yes

4

Yes

No

Yes

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

`mozClearDataAt`

No

No

3.5-71

No

No

No

No

No

4-79

No

No

No

`mozCursor`

No

No

3.5

No

No

No

No

No

4

No

No

No

`mozGetDataAt`

No

No

3.5-71

No

No

No

No

No

4-79

No

No

No

`mozItemCount`

No

No

3.5-71

No

No

No

No

No

4-79

No

No

No

`mozSetDataAt`

No

No

3.5-71

No

No

No

No

No

4-79

No

No

No

`mozSourceNode`

No

No

4

No

No

No

No

No

4

No

No

No

`mozTypesAt`

No

No

3.5-71

No

No

No

No

No

4-79

No

No

No

`mozUserCancelled`

No

No

3.5

No

No

No

No

No

4

No

No

No

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

`setDragImage`

Yes

18

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

- [Drag and drop](html_drag_and_drop_api)
- [Drag Operations](html_drag_and_drop_api/drag_operations)
- [Recommended Drag Types](html_drag_and_drop_api/recommended_drag_types)
- [Dragging and Dropping Multiple Items](html_drag_and_drop_api/multiple_items)
- [DataTransfer test - Paste or Drag](https://codepen.io/tech_query/pen/MqGgap)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer</a>
