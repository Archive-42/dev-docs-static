# Element.getElementsByTagName()

The `Element.getElementsByTagName()` method returns a live [`HTMLCollection`](../htmlcollection) of elements with the given [tag name](tagname). All descendants of the specified element are searched, but not the element itself. The returned list is _live_, which means it updates itself with the DOM tree automatically. Therefore, there is no need to call `Element.getElementsByTagName()` with the same element and arguments repeatedly if the DOM changes in between calls.

When called on an HTML element in an HTML document, `getElementsByTagName` lower-cases the argument before searching for it. This is undesirable when trying to match camel-cased SVG elements (such as `<linearGradient>`) in an HTML document. Instead, use [`Element.getElementsByTagNameNS()`](getelementsbytagnamens), which preserves the capitalization of the tag name.

`Element.getElementsByTagName` is similar to [`Document.getElementsByTagName()`](../document/getelementsbytagname), except that it only searches for elements that are descendants of the specified element.

## Syntax

    elements = element.getElementsByTagName(tagName)

- `elements` is a _live_ [`HTMLCollection`](../htmlcollection) of elements with a matching tag name, in the order they appear. If no elements are found, the `HTMLCollection` is empty.
- `element` is the element from where the search starts. Only the element's descendants are included, not the element itself.
- `tagName` is the qualified name to look for. The special string `"*"` represents all elements. For compatibility with XHTML, lower-case should be used.

## Example

    // Check the status of each data cell in a table
    const table = document.getElementById('forecast-table');
    const cells = table.getElementsByTagName('td');

    for (let cell of cells) {
      let status = cell.getAttribute('data-status');
      if (status === 'open') {
        // Grab the data
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-getelementsbytagname">DOM<br />
<span class="small">The definition of 'Element.getElementsByTagName()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Changed the return value from <a href="../nodelist"><code>NodeList</code></a> to <a href="../htmlcollection"><code>HTMLCollection</code></a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-1938918D">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Element.getElementsByTagName()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Core/">Document Object Model (DOM) Level 2 Core Specification</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-1938918D">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Element.getElementsByTagName()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#ID-1938918D">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'Element.getElementsByTagName()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`getElementsByTagName`

1

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

12

1

Prior to Firefox 19, this method was returning a `NodeList`; it was then changed to reflect the change in the spec.

5.5

8

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

1

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

1

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

18

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

4

Prior to Firefox 19, this method was returning a `NodeList`; it was then changed to reflect the change in the spec.

10.1

1

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

1.0

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

`all_elements_selector`

1

12

Yes

6

Yes

Yes

1

Yes

Yes

Prior to Firefox 19, this method was returning a `NodeList`; it was then changed to reflect the change in the spec.

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByTagName" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByTagName</a>
