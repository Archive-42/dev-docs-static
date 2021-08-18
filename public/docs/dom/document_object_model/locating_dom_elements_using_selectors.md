# Locating DOM elements using selectors

The Selectors API provides methods that make it quick and easy to retrieve [`Element`](../element) nodes from the DOM by matching against a set of selectors. This is much faster than past techniques, wherein it was necessary to, for example, use a loop in JavaScript code to locate the specific items you needed to find.

## The NodeSelector interface

This specification adds two new methods to any objects implementing the [`Document`](../document), [`DocumentFragment`](../documentfragment), or [`Element`](../element) interfaces:

[`querySelector()`](../element/queryselector)  
Returns the first matching [`Element`](../element) node within the node's subtree. If no matching node is found, `null` is returned.

[`querySelectorAll()`](../element/queryselectorall)  
Returns a [`NodeList`](../nodelist) containing all matching `Element` nodes within the node's subtree, or an empty `NodeList` if no matches are found.

**Note:** The [`NodeList`](../nodelist) returned by [`querySelectorAll()`](../element/queryselectorall) is not live, which means that changes in the DOM are not reflected in the collection. This is different from other DOM querying methods that return live node lists.

You may find examples and details by reading the documentation for the [`Element.querySelector()`](../element/queryselector) and [`Element.querySelectorAll()`](../element/queryselectorall) methods.

## Selectors

The selector methods accept one or more comma-separated selectors to determine what element or elements should be returned. For example, to select all paragraph (`p`) elements in a document whose CSS class is either `warning` or `note`, you can do the following:

    var special = document.querySelectorAll("p.warning, p.note");

You can also query by ID. For example:

    var el = document.querySelector("#main, #basic, #exclamation");

After executing the above code, `el` contains the first element in the document whose ID is one of `main`, `basic`, or `exclamation`.

You may use any CSS selectors with the `querySelector()` and `querySelectorAll()` methods.

## See also

- [Selectors API](https://www.w3.org/TR/selectors-api/)
- [`Element.querySelector()`](../element/queryselector)
- [`Element.querySelectorAll()`](../element/queryselectorall)
- [`Document.querySelector()`](../document/queryselector)
- [`Document.querySelectorAll()`](../document/queryselectorall)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document_object_model/Locating_DOM_elements_using_selectors" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document_object_model/Locating_DOM_elements_using_selectors</a>
