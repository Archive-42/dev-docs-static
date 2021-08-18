# DataTransferItemList

The `DataTransferItemList` object is a list of [`DataTransferItem`](datatransferitem) objects representing items being dragged. During a _drag operation_, each [`DragEvent`](dragevent) has a [`dataTransfer`](dragevent/datatransfer) property and that property is a `DataTransferItemList`.

This interface has no constructor.

## Properties

[`DataTransferItemList.length`](datatransferitemlist/length) <span class="badge inline readonly">Read only </span>  
An `unsigned long` that is the number of drag items in the list.

## Methods

[`DataTransferItemList.add()`](datatransferitemlist/add)  
Adds an item (either a [`File`](file) object or a [`string`](domstring)) to the drag item list and returns a [`DataTransferItem`](datatransferitem) object for the new item.

[`DataTransferItemList.remove()`](datatransferitemlist/remove)  
Removes the drag item from the list at the given index.

[`DataTransferItemList.clear()`](datatransferitemlist/clear)  
Removes all of the drag items from the list.

[`DataTransferItemList.DataTransferItem()`](datatransferitemlist/datatransferitem)  
Getter that returns a [`DataTransferItem`](datatransferitem) at the given index.

## Example

Each of this interface's methods and properties has a reference page, and each reference page has an example of its usage.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#datatransferitemlist">HTML Living Standard<br />
<span class="small">The definition of 'DataTransferItemList' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/editing.html#datatransferitemlist">HTML 5.1<br />
<span class="small">The definition of 'DataTransferItemList' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Not included in W3C HTML5 <span class="spec-rec">Recommendation</span></td></tr></tbody></table>

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

`DataTransferItemList`

13

12

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

`add`

13

12

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

`clear`

13

12

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

`length`

13

12

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

`remove`

31

12

50

No

12

6

4.4.3

31

50

No

6

2.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransferItemList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransferItemList</a>
