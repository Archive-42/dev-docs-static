# HTMLCollection.item

The [`HTMLCollection`](../htmlcollection) method `item()` returns the node located at the specified offset into the collection.

**Note:** Because the contents of an `HTMLCollection` are live, changes to the underlying DOM can and will cause the position of individual nodes in the collection to change, so the index value will not necessarily remain constant for a given node.

## Syntax

    var element = HTMLCollection.item(index)

### Parameters

`index`  
The position of the [`Node`](../node) to be returned. Elements appear in an `HTMLCollection` in the same order in which they appear in the document's source.

### Return value

The [`Node`](../node) at the specified index, or `null` if `index` is less than zero or greater than or equal to the length property.

## Usage notes

The `item()` method returns a numbered element from an `HTMLCollection`. In JavaScript, it is easier to treat the `HTMLCollection` as an array and to index it using array notation. See the [example](#example) below.

## Example

    var c = document.images;  // This is an HTMLCollection
    var img0 = c.item(0);     // You can use the item() method this way
    var img1 = c[1];          // But this notation is easier and more common

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

`item`

1

12

1

8

≤12.1

1

1

18

4

≤12.1

1

1.0

## See also

- [`NodeList.item()`](../nodelist/item)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection/item" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection/item</a>
