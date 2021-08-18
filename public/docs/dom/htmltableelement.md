# HTMLTableElement

The `HTMLTableElement` interface provides special properties and methods (beyond the regular [`HTMLElement`](htmlelement) object interface it also has available to it by inheritance) for manipulating the layout and presentation of tables in an HTML document.

## Properties

_Inherits properties from its parent, [`HTMLElement`](htmlelement)._

[`HTMLTableElement.caption`](htmltableelement/caption)  
Is a [`HTMLTableCaptionElement`](htmltablecaptionelement) representing the first [`<caption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption) that is a child of the element, or `null` if none is found. When set, if the object doesn't represent a `<caption>`, a [`DOMException`](domexception) with the `HierarchyRequestError` name is thrown. If a correct object is given, it is inserted in the tree as the first child of this element and the first `<caption>` that is a child of this element is removed from the tree, if any.

[`HTMLTableElement.tHead`](htmltableelement/thead)  
Is a [`HTMLTableSectionElement`](htmltablesectionelement) representing the first [`<thead>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/thead) that is a child of the element, or `null` if none is found. When set, if the object doesn't represent a `<thead>`, a [`DOMException`](domexception) with the `HierarchyRequestError` name is thrown. If a correct object is given, it is inserted in the tree immediately before the first element that is neither a [`<caption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption), nor a [`<colgroup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/colgroup), or as the last child if there is no such element, and the first `<thead>` that is a child of this element is removed from the tree, if any.

[`HTMLTableElement.tFoot`](htmltableelement/tfoot)  
Is a [`HTMLTableSectionElement`](htmltablesectionelement) representing the first [`<tfoot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tfoot) that is a child of the element, or `null` if none is found. When set, if the object doesn't represent a `<tfoot>`, a [`DOMException`](domexception) with the `HierarchyRequestError` name is thrown. If a correct object is given, it is inserted in the tree immediately before the first element that is neither a [`<caption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption), a [`<colgroup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/colgroup), nor a [`<thead>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/thead), or as the last child if there is no such element, and the first `<tfoot>` that is a child of this element is removed from the tree, if any.

[`HTMLTableElement.rows`](htmltableelement/rows)<span class="badge inline readonly">Read only </span>  
Returns a live [`HTMLCollection`](htmlcollection) containing all the rows of the element, that is all [`<tr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr) that are a child of the element, or a child of one of its [`<thead>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/thead), [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody) and [`<tfoot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tfoot) children. The rows members of a `<thead>` appear first, in tree order, and those members of a `<tbody>` last, also in tree order. The `HTMLCollection` is live and is automatically updated when the `HTMLTableElement` changes.

[`HTMLTableElement.tBodies`](htmltableelement/tbodies)<span class="badge inline readonly">Read only </span>  
Returns a live [`HTMLCollection`](htmlcollection) containing all the [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody) of the element. The `HTMLCollection` is live and is automatically updated when the `HTMLTableElement` changes.

### Obsolete Properties

**Warning:** The following properties are obsolete. You should avoid using them.

[`HTMLTableElement.align`](htmltableelement/align) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) containing an enumerated value reflecting the [`align`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table#attr-align) attribute. It indicates the alignment of the element's contents with respect to the surrounding context. The possible values are `"left"`, `"right"`, and `"center"`.

[`HTMLTableElement.bgColor`](htmltableelement/bgcolor) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) containing the background color of the cells. It reflects the obsolete [`bgcolor`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table#attr-bgcolor) attribute.

[`HTMLTableElement.border`](htmltableelement/border) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) containing the width in pixels of the border of the table. It reflects the obsolete [`border`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table#attr-border) attribute.

[`HTMLTableElement.cellPadding`](htmltableelement/cellpadding) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) containing the width in pixels of the horizontal and vertical sapce between cell content and cell borders. It reflects the obsolete [`cellpadding`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table#attr-cellpadding) attribute.

[`HTMLTableElement.cellSpacing`](htmltableelement/cellspacing) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) containing the width in pixels of the horizontal and vertical separation between cells. It reflects the obsolete [`cellspacing`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table#attr-cellspacing) attribute.

[`HTMLTableElement.frame`](htmltableelement/frame) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) containing the type of the external borders of the table. It reflects the obsolete [`frame`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table#attr-frame) attribute and can take one of the following values: `"void"`, `"above"`, `"below"`, `"hsides"`, `"vsides"`, `"lhs"`, `"rhs"`, `"box"`, or `"border"`.

[`HTMLTableElement.rules`](htmltableelement/rules) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) containing the type of the internal borders of the table. It reflects the obsolete [`rules`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table#attr-rules) attribute and can take one of the following values: `"none"`, `"groups"`, `"rows"`, `"cols"`, or `"all"`.

[`HTMLTableElement.summary`](htmltableelement/summary) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) containing a description of the purpose or the structure of the table. It reflects the obsolete [`summary`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table#attr-summary) attribute.

[`HTMLTableElement.width`](htmltableelement/width) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) containing the length in pixels or in percentage of the desired width fo the entire table. It reflects the obsolete [`width`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table#attr-width) attribute.

## Methods

_Inherits methods from its parent, [`HTMLElement`](htmlelement)_.

[`HTMLTableElement.createTHead()`](htmltableelement/createthead)  
Returns an [`HTMLTableSectionElement`](htmltablesectionelement) representing the first [`<thead>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/thead) that is a child of the element. If none is found, a new one is created and inserted in the tree immediately before the first element that is neither a [`<caption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption), nor a [`<colgroup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/colgroup), or as the last child if there is no such element.

[`HTMLTableElement.deleteTHead()`](htmltableelement/deletethead)  
Removes the first [`<thead>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/thead) that is a child of the element.

[`HTMLTableElement.createTFoot()`](htmltableelement/createtfoot)  
Returns an [`HTMLTableSectionElement`](htmltablesectionelement) representing the first [`<tfoot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tfoot) that is a child of the element. If none is found, a new one is created and inserted in the tree as the last child.

[`HTMLTableElement.deleteTFoot()`](htmltableelement/deletetfoot)  
Removes the first [`<tfoot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tfoot) that is a child of the element.

[`HTMLTableElement.createTBody()`](htmltableelement/createtbody)  
Returns a [`HTMLTableSectionElement`](htmltablesectionelement) representing a new [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody) that is a child of the element. It is inserted in the tree after the last element that is a [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody), or as the last child if there is no such element.

[`HTMLTableElement.createCaption()`](htmltableelement/createcaption)  
Returns an [`HTMLElement`](htmlelement) representing the first [`<caption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption) that is a child of the element. If none is found, a new one is created and inserted in the tree as the first child of the [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table) element.

[`HTMLTableElement.deleteCaption()`](htmltableelement/deletecaption)  
Removes the first [`<caption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption) that is a child of the element.

[`HTMLTableElement.insertRow()`](htmltableelement/insertrow)  
Returns an [`HTMLTableRowElement`](htmltablerowelement) representing a new row of the table. It inserts it in the rows collection immediately before the [`<tr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr) element at the given `index` position. If necessary a [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody) is created. If the `index` is `-1`, the new row is appended to the collection. If the `index` is smaller than `-1` or greater than the number of rows in the collection, a [`DOMException`](domexception) with the value `IndexSizeError` is raised.

[`HTMLTableElement.deleteRow()`](htmltableelement/deleterow)  
Removes the row corresponding to the `index` given in parameter. If the `index` value is `-1` the last row is removed; if it smaller than `-1` or greater than the amount of rows in the collection, a [`DOMException`](domexception) with the value `IndexSizeError` is raised.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmltableelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLTableElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added the <code>sortable</code> property and the <code>stopSorting()</code> method.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/tabular-data.html#the-table-element">HTML5<br />
<span class="small">The definition of 'HTMLTableElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Added the <code>createTBody()</code> method.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-64060425">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLTableElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Defined when <code>caption</code>, <code>tHead</code>, <code>tFoot</code>, <code>insertRow()</code>, and <code>deleteRow()</code> raise exceptions.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-64060425">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLTableElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`HTMLTableElement`

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

`align`

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

`bgColor`

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

`border`

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

`caption`

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

`cellPadding`

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

`cellSpacing`

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

`createCaption`

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

`createTBody`

20

12

25

9

15

6

≤37

25

25

14

6

1.5

`createTFoot`

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

`createTHead`

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

`deleteCaption`

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

`deleteRow`

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

`deleteTFoot`

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

`deleteTHead`

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

`frame`

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

`insertRow`

1

12

1

Starting with Firefox 20, the index argument has been made optional and defaults to -1 as per HTML specification.

5.5

10

4

1

18

4

Starting with Firefox 20, the index argument has been made optional and defaults to -1 as per HTML specification.

10.1

3

1.0

`rows`

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

`rules`

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

`summary`

1

12

1

6

≤12.1

3

1

18

4

≤12.1

1

1.0

`tBodies`

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

`tFoot`

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

`width`

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

## See also

- The HTML element implementing this interface: [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement</a>
