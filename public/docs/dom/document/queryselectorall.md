# Document.querySelectorAll()

The [`Document`](../document) method `querySelectorAll()` returns a static (not live) [`NodeList`](../nodelist) representing a list of the document's elements that match the specified group of selectors.

**Note:** This method is implemented based on the [`ParentNode`](../parentnode) mixin's [`querySelectorAll()`](../parentnode/queryselectorall) method.

## Syntax

    elementList = parentNode.querySelectorAll(selectors);

### Parameters

`selectors`  
A [`DOMString`](../domstring) containing one or more selectors to match against. This string must be a valid [CSS selector](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors) string; if it's not, a `SyntaxError` exception is thrown. See [Locating DOM elements using selectors](../document_object_model/locating_dom_elements_using_selectors) for more information about using selectors to identify elements. Multiple selectors may be specified by separating them using commas.

**Note:** Characters which are not part of standard CSS syntax must be escaped using a backslash character. Since JavaScript also uses backslash escaping, special care must be taken when writing string literals using these characters. See [Escaping special characters](queryselector#escaping_special_characters) for more information.

### Return value

A non-live [`NodeList`](../nodelist) containing one [`Element`](../element) object for each element that matches at least one of the specified selectors or an empty [`NodeList`](../nodelist) in case of no matches.

**Note:** If the specified `selectors` include a [CSS pseudo-element](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements), the returned list is always empty.

### Exceptions

`SyntaxError`  
The syntax of the specified `selectors` string is not valid.

## Examples

### Obtaining a list of matches

To obtain a [`NodeList`](../nodelist) of all of the [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) elements in the document:

    const matches = document.querySelectorAll("p");

This example returns a list of all [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) elements within the document with a class of either `note` or `alert`:

    const matches = document.querySelectorAll("div.note, div.alert");

Here, we get a list of `<p>` elements whose immediate parent element is a [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) with the class `highlighted` and which are located inside a container whose ID is `test`.

    const container = document.querySelector("#test");
    const matches = container.querySelectorAll("div.highlighted > p");

This example uses an [attribute selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors) to return a list of the [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) elements in the document that contain an attribute named `data-src`:

    const matches = document.querySelectorAll("iframe[data-src]");

Here, an attribute selector is used to return a list of the list items contained within a list whose ID is `userlist` which have a `data-active` attribute whose value is `1`:

    const container = document.querySelector("#userlist");
    const matches = container.querySelectorAll("li[data-active='1']");

### Accessing the matches

Once the [`NodeList`](../nodelist) of matching elements is returned, you can examine it just like any array. If the array is empty (that is, its `length` property is 0), then no matches were found.

Otherwise, you can use standard array notation to access the contents of the list. You can use any common looping statement, such as:

    const highlightedItems = userList.querySelectorAll(".highlighted");

    highlightedItems.forEach(function(userItem) {
      deleteUser(userItem);
    });

## User notes

`querySelectorAll()` behaves differently than most common JavaScript DOM libraries, which might lead to unexpected results.

### HTML

Consider this HTML, with its three nested [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) blocks.

    <div class="outer">
      <div class="select">
        <div class="inner">
        </div>
      </div>
    </div>

### JavaScript

    const select = document.querySelector('.select');
    const inner = select.querySelectorAll('.outer .inner');
    inner.length; // 1, not 0!

In this example, when selecting `.outer .inner` in the context the `<div>` with the class `select`, the element with the class `.inner` is still found, even though `.outer` is not a descendant of the base element on which the search is performed (`.select`). By default, `querySelectorAll()` only verifies that the last element in the selector is within the search scope.

The [`:scope`](https://developer.mozilla.org/en-US/docs/Web/CSS/:scope) pseudo-class restores the expected behavior, only matching selectors on descendants of the base element:

    const select = document.querySelector('.select');
    const inner = select.querySelectorAll(':scope .outer .inner');
    inner.length; // 0

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-parentnode-queryselectorall">DOM<br />
<span class="small">The definition of 'ParentNode.querySelectorAll()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Living standard</td></tr><tr class="even"><td><a href="https://dev.w3.org/2006/webapi/selectors-api2/#dom-parentnode-queryselectorall">Selectors API Level 2<br />
<span class="small">The definition of 'ParentNode.querySelectorAll()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/dom/#dom-parentnode-queryselectorall">DOM4<br />
<span class="small">The definition of 'ParentNode.querySelectorAll()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/selectors-api/#interface-definitions">Selectors API Level 1<br />
<span class="small">The definition of 'document.querySelector()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Original definition</td></tr></tbody></table>

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

3.1

1

18

4

10.1

2

1.0

## See also

- [Locating DOM elements using selectors](../document_object_model/locating_dom_elements_using_selectors)
- [Attribute selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors) in the CSS Guide
- [Attribute selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Attribute_selectors) in the MDN Learning Area
- [`Element.querySelector()`](../element/queryselector) and [`Element.querySelectorAll()`](../element/queryselectorall)
- [`Document.querySelector()`](queryselector)
- [`DocumentFragment.querySelector()`](../documentfragment/queryselector) and [`DocumentFragment.querySelectorAll()`](../documentfragment/queryselectorall)
- [`ParentNode.querySelector()`](../parentnode/queryselector) and [`ParentNode.querySelectorAll()`](../parentnode/queryselectorall)
- [Code snippets for `querySelector()`](https://developer.mozilla.org/en-US/docs/Code_snippets/QuerySelector)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll</a>
