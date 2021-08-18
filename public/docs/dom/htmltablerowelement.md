HTMLTableRowElement
===================

The `HTMLTableRowElement` interface provides special properties and methods (beyond the [`HTMLElement`](htmlelement) interface it also has available to it by inheritance) for manipulating the layout and presentation of rows in an HTML table.

Properties
----------

*Inherits properties from its parent, [`HTMLElement`](htmlelement).*

 <span class="page-not-created">`HTMLTableRowElement.cells`</span> <span class="badge inline readonly">Read only </span>   
Returns a live [`HTMLCollection`](htmlcollection) containing the cells in the row. The `HTMLCollection` is live and is automatically updated when cells are added or removed.

 [`HTMLTableRowElement.rowIndex`](htmltablerowelement/rowindex) <span class="badge inline readonly">Read only </span>   
Returns a `long` value which gives the logical position of the row within the entire table. If the row is not part of a table, returns `-1`.

 <span class="page-not-created">`HTMLTableRowElement.sectionRowIndex`</span> <span class="badge inline readonly">Read only </span>   
Returns a `long` value which gives the logical position of the row within the table section it belongs to. If the row is not part of a section, returns `-1`.

Methods
-------

*Inherits methods from its parent, [`HTMLElement`](htmlelement)*.

<span class="page-not-created">`HTMLTableRowElement.deleteCell()`</span>  
Removes the cell at the given position in the row. If the given position is greater (or equal as it starts at zero) than the amount of cells in the row, or is smaller than `0`, it raises a [`DOMException`](domexception) with the `IndexSizeError` value.

[`HTMLTableRowElement.insertCell()`](htmltablerowelement/insertcell)  
Inserts a new cell just before the given position in the row. If the given position is not given or is `-1`, it appends the cell to the row. If the given position is greater (or equal as it starts at zero) than the amount of cells in the row, or is smaller than `-1`, it raises a [`DOMException`](domexception) with the `IndexSizeError` value. Returns a reference to a [`HTMLTableCellElement`](htmltablecellelement).

Deprecated properties
---------------------

**Warning:** These properties have been <span class="page-not-created">deprecated</span> and should no longer be used. They are documented primarily to help understand older code bases.

 <span class="page-not-created">`HTMLTableRowElement.align`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`DOMString`](domstring) containing an enumerated value reflecting the [`align`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr#attr-align) attribute. It indicates the alignment of the element's contents with respect to the surrounding context. The possible values are `"left"`, `"right"`, and `"center"`.

 <span class="page-not-created">`HTMLTableRowElement.bgColor`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`DOMString`](domstring) containing the background color of the cells. It reflects the obsolete [`bgcolor`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr#attr-bgcolor) attribute.

 <span class="page-not-created">`HTMLTableRowElement.ch`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`DOMString`](domstring) containing one single character. This character is the one to align all the cell of a column on. It reflects the [`char`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr#attr-char) and default to the decimal points associated with the language, e.g. `'.'` for English, or `','` for French. This property was optional and was not very well supported.

 <span class="page-not-created">`HTMLTableRowElement.chOff`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`DOMString`](domstring) containing a integer indicating how many characters must be left at the right (for left-to-right scripts; or at the left for right-to-left scripts) of the character defined by `HTMLTableRowElement.ch`. This property was optional and was not very well supported.

 <span class="page-not-created">`HTMLTableRowElement.vAlign`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`DOMString`](domstring) representing an enumerated value indicating how the content of the cell must be vertically aligned. It reflects the [`valign`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr#attr-valign) attribute and can have one of the following values: `"top"`, `"middle"`, `"bottom"`, or `"baseline"`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmltablerowelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLTableRowElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/tabular-data.html#the-tr-element">HTML5<br />
<span class="small">The definition of 'HTMLTableRowElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The parameter of <code>insertCell</code> is now optional and default to <code>-1</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-6986576">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLTableRowElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>The <code>cells</code>, <code>rowIndex</code>, and <code>selectionRowIndex</code> properties are now read-only.<br />
The methods <code>insertCell</code> and <code>deleteCell</code> can raise exceptions.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-6986576">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLTableRowElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`HTMLTableRowElement`

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

`cells`

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

`ch`

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

`chOff`

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

`deleteCell`

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

`insertCell`

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

`rowIndex`

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

`sectionRowIndex`

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

`vAlign`

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

-   The HTML element implementing this interface: [`<tr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableRowElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableRowElement</a>
