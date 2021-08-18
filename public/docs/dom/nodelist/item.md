# NodeList.item()

Returns a node from a [`NodeList`](../nodelist) by index. This method doesn't throw exceptions as long as you provide arguments. A value of `null` is returned if the index is out of range, and a `TypeError` is thrown if no argument is provided.

## Syntax

    nodeItem = nodeList.item(index)

- `nodeList` is a `NodeList`. This is usually obtained from another DOM property or method, such as [childNodes](../node/childnodes).
- `index` is the index of the node to be fetched. The index is zero-based.
- `nodeItem` is the `index`th node in the `nodeList` returned by the `item` method.

## Alternate Syntax

JavaScript also offers an array-like bracketed syntax for obtaining an item from a NodeList by index:

    nodeItem = nodeList[index]

## Example

    var tables = document.getElementsByTagName("table");
    var firstTable = tables.item(1); // or tables[1] - returns the second table in the DOM

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-nodelist-item">DOM<br />
<span class="small">The definition of 'NodeList: item' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

5

Yes

1

Yes

Yes

4

Yes

1

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NodeList/item" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NodeList/item</a>
