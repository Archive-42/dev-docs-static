HTMLTableElement.tHead
======================

The `HTMLTableElement.tHead` represents the [`<thead>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/thead) element of a [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table) . Its value will be `null` if there is no such element.

Syntax
------

    thead_element = table.tHead;
    table.tHead = thead_element;

### Parameters

-   `thead_element` is a [`HTMLTableSectionElement`](../htmltablesectionelement).

Example
-------

    if (table.tHead == my_head_el) {
      // ...
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/tabular-data.html#dom-table-thead">HTML Living Standard<br />
<span class="small">The definition of 'HTMLTableElement.tHead' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/tabular-data.html#dom-table-thead">HTML5<br />
<span class="small">The definition of 'HTMLTableElement.tHead' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-HTML/">Document Object Model (DOM) Level 2 HTML Specification</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-9530944">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLTableElement.tHead' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-9530944">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLTableElement.tHead' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`tHead`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

See also
--------

-   The interface implementing this property: [`HTMLTableElement`](../htmltableelement).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/tHead" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/tHead</a>
