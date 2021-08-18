# DocumentFragment.querySelectorAll()

The `DocumentFragment.querySelectorAll()` method returns a [`NodeList`](../nodelist) of elements within the [`DocumentFragment`](../documentfragment) (using depth-first pre-order traversal of the document's nodes) that matches the specified group of selectors.

If the selectors specified in parameter are invalid a [`DOMException`](../domexception) with a `SYNTAX_ERR` value is raised.

**Note:** The definition of this API was moved to the [`ParentNode`](../parentnode) interface.

## Syntax

    elementList = documentfragment.querySelectorAll(selectors);

### Parameters

_selectors_  
Is a [`DOMString`](../domstring) containing one or more CSS selectors separated by commas.

## Examples

This example returns a list of all `div` elements within the `DocumentFragment` with a class of either "`note`" or "`alert`":

    var matches = documentfrag.querySelectorAll("div.note, div.alert");

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/selectors-api/#queryselector">Selectors API Level 1<br />
<span class="small">The definition of 'DocumentFragment.querySelectorAll' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`querySelectorAll`

1

12

3.5

9

8

`querySelectorAll()` is supported, but only for CSS 2.1 selectors.

10

4

1

18

4

10.1

3

1.0

## See also

- The [`DocumentFragment`](../documentfragment) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment/querySelectorAll" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment/querySelectorAll</a>
