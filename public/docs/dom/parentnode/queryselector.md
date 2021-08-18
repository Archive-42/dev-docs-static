# ParentNode.querySelector()

**Draft**

This page is not complete.

The [`ParentNode`](../parentnode) mixin defines the `querySelector()` method as returning an [`Element`](../element) representing the first element matching the specified group of selectors which are descendants of the object on which the method was called.

If you need all the elements matching the selector list, use [`querySelectorAll()`](queryselectorall) instead.

**Note:** This method is implemented as [`Document.querySelector()`](../document/queryselector), [`DocumentFragment.querySelector()`](../documentfragment/queryselector) and [`Element.querySelector()`](../element/queryselector).

## Syntax

    element = parentNode.querySelector(selectors);

### Parameters

`selectors`  
A [`DOMString`](../domstring) containing one or more selectors to match against. This string must be a valid [compound selector list](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors) supported by the browser; if it's not, a `SyntaxError` exception is thrown. See [Locating DOM elements using selectors](../document_object_model/locating_dom_elements_using_selectors) for more information about using selectors to identify elements. Multiple selectors may be specified by separating them using commas.

**Note:** Characters which are not part of standard CSS syntax must be escaped using a backslash character. Since JavaScript also uses backspace escaping, special care must be taken when writing string literals using these characters. See [Escaping special characters](#escaping_special_characters) for more information.

### Return value

The first [`Element`](../element) that matches at least one of the specified selectors or `null` if no such element is found.

**Note:** If the specified `selectors` include a [CSS pseudo-element](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements), the returned value is always `null`.

### Exceptions

`SyntaxError`  
The syntax of the specified `selectors` string is not valid.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-parentnode-queryselector">DOM<br />
<span class="small">The definition of 'ParentNode.querySelector()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Living standard</td></tr><tr class="even"><td><a href="https://dev.w3.org/2006/webapi/selectors-api2/#dom-parentnode-queryselector">Selectors API Level 2<br />
<span class="small">The definition of 'ParentNode.querySelector()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/dom/#dom-parentnode-queryselector">DOM4<br />
<span class="small">The definition of 'ParentNode.querySelector()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/selectors-api/#interface-definitions">Selectors API Level 1<br />
<span class="small">The definition of 'document.querySelector()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Original definition</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.ParentNode.querySelector`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [Locating DOM elements using selectors](../document_object_model/locating_dom_elements_using_selectors)
- [Code snippets for `querySelector()`](https://developer.mozilla.org/en-US/docs/Code_snippets/QuerySelector)
- [Attribute selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors) in the CSS Guide
- [Attribute selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Attribute_selectors) in the MDN Learning Area
- This method is available as [`Element.querySelector()`](../element/queryselector), [`Document.querySelector()`](../document/queryselector), and [`DocumentFragment.querySelector()`](../documentfragment/queryselector)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ParentNode/querySelector" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ParentNode/querySelector</a>
