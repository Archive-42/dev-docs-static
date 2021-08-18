# Element.querySelector()

The `querySelector()` method of the [`Element`](../element) interface returns the first element that is a descendant of the element on which it is invoked that matches the specified group of selectors.

## Syntax

    element = baseElement.querySelector(selectors);

### Parameters

`selectors`  
A group of [selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors) to match the descendant elements of the [`Element`](../element) `baseElement` against; this must be valid CSS syntax, or a `SyntaxError` exception will occur. The first element found which matches this group of selectors is returned.

### Return value

The first descendant element of `baseElement` which matches the specified group of `selectors`. The entire hierarchy of elements is considered when matching, including those outside the set of elements including `baseElement` and its descendants; in other words, `selectors` is first applied to the whole document, not the `baseElement`, to generate an initial list of potential elements. The resulting elements are then examined to see if they are descendants of `baseElement`. The first match of those remaining elements is returned by the `querySelector()` method.

If no matches are found, the returned value is `null`.

### Exceptions

`SyntaxError`  
The specified `selectors` are invalid.

## Examples

Let's consider a few examples.

### Find a specific element with specific values of an attribute

In this first example, the first [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style) element which either has no type or has type "text/css" in the HTML document body is returned:

    var el = document.body.querySelector("style[type='text/css'], style:not([type])");

### The entire hierarchy counts

This example demonstrates that the hierarchy of the entire document is considered when applying `selectors`, so that levels outside the specified `baseElement` are still considered when locating matches.

#### HTML

    <div>
      <h5>Original content</h5>
      <p>
        inside paragraph
        <span>inside span</span>
        inside paragraph
      </p>
    </div>
    <div>
      <h5>Output</h5>
      <div id="output"></div>
    </div>

#### JavaScript

    var baseElement = document.querySelector("p");
    document.getElementById("output").innerHTML =
      (baseElement.querySelector("div span").innerHTML);

#### Result

The result looks like this:

Notice how the `"div span"` selector still successfully matches the [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) element, even though the `baseElement`'s child nodes do not include the <span class="page-not-created">`div`</span> element (it is still part of the specified selector).

### More examples

See [`Document.querySelector()`](../document/queryselector) for additional examples of the proper format for the `selectors`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-parentnode-queryselectorall">DOM<br />
<span class="small">The definition of 'querySelector()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://dev.w3.org/2006/webapi/selectors-api2/#queryselectorall">Selectors API Level 2<br />
<span class="small">The definition of 'querySelectorAll()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/selectors-api/#queryselectorall">Selectors API Level 1<br />
<span class="small">The definition of 'querySelectorAll()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr></tbody></table>

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

`querySelector`

1

12

3.5

9

8

`querySelector()` is supported, but only for CSS 2.1 selectors.

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
- [`Element.querySelectorAll()`](queryselectorall)
- [`Document.querySelector()`](../document/queryselector) and [`Document.querySelectorAll()`](../document/queryselectorall)
- [`DocumentFragment.querySelector()`](../documentfragment/queryselector) and [`DocumentFragment.querySelectorAll()`](../documentfragment/queryselectorall)
- [`ParentNode.querySelector()`](../parentnode/queryselector) and [`ParentNode.querySelectorAll()`](../parentnode/queryselectorall)
- [Code snippets for querySelector](https://developer.mozilla.org/en-US/docs/Code_snippets/QuerySelector)
- Other methods that take selectors: [`element.closest()`](closest) and [`element.matches()`](matches).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelector" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelector</a>
