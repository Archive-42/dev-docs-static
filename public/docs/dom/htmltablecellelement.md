# HTMLTableCellElement

The `HTMLTableCellElement` interface provides special properties and methods (beyond the regular [`HTMLElement`](htmlelement) interface it also has available to it by inheritance) for manipulating the layout and presentation of table cells, either header or data cells, in an HTML document.

## Properties

_Inherits properties from its parent, [`HTMLElement`](htmlelement)._

<span class="page-not-created">`HTMLTableCellElement.abbr`</span>  
A [`DOMString`](domstring) which can be used on `<th>` elements (not on [`<td>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td)), specifying an alternative label for the header cell. This alternate label can be used in other contexts, such as when describing the headers that apply to a data cell. This is used to offer a shorter term for use by screen readers in particular, and is a valuable accessibility tool. Usually the value of `abbr` is an abbreviation or acronym, but can be any text that's appropriate contextually.

<span class="page-not-created">`HTMLTableCellElement.cellIndex`</span> <span class="badge inline readonly">Read only </span>  
A long integer representing the cell's position in the <span class="page-not-created">`cells`</span> collection of the [`<tr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr) the cell is contained within. If the cell doesn't belong to a `<tr>`, it returns `-1`.

<span class="page-not-created">`HTMLTableCellElement.colSpan`</span>  
An unsigned long integer indicating the number of columns this cell must span; this lets the cell occupy space across multiple columns of the table. It reflects the [`colspan`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td#attr-colspan) attribute.

<span class="page-not-created">`HTMLTableCellElement.headers`</span> <span class="badge inline readonly">Read only </span>  
Is a <span class="page-not-created">`DOMSettableTokenList`</span> describing a list of `id` of [`<th>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/th) elements that represents headers associated with the cell. It reflects the [`headers`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td#attr-headers) attribute.

<span class="page-not-created">`HTMLTableCellElement.rowSpan`</span>  
An unsigned long integer indicating the number of rows this cell must span; this lets a cell occupy space across multiple rows of the table. It reflects the [`rowspan`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td#attr-rowspan) attribute.

<span class="page-not-created">`HTMLTableCellElement.scope`</span>  
A [`DOMString`](domstring) indicating the scope of a [`<th>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/th) cell. Header cells can be configured, using the `scope` property, the apply to a specified row or column, or to the not-yet-scoped cells within the current row group (that is, the same ancestor [`<thead>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/thead), [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody), or [`<tfoot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tfoot) element). If no value is specified for `scope`, the header is not associated directly with cells in this way. Permitted values for `scope` are:

`col`  
The header cell applies to the following cells in the same column (or columns, if `colspan` is used as well), until either the end of the column or another `<th>` in the column establishes a new scope.

`colgroup`  
The header cell applies to all cells in the current column group that do not already have a scope applied to them. This value is only allowed if the cell is in a column group.

`row`  
The header cell applies to the following cells in the same row (or rows, if `rowspan` is used as well), until either the end of the row or another `<th>` in the same row establishes a new scope.

`rowgroup`  
The header cell applies to all cells in the current row group that do not already have a scope applied to them. This value is only allowed if the cell is in a row group.

The empty string (`""`)  
The header cell has no predefined scope; the user agent will establish the scope based on contextual clues.

## Methods

_No specific method; inherits methods from its parent, [`HTMLElement`](htmlelement)_.

## Deprecated properties

**Warning:** These properties have been <span class="page-not-created">deprecated</span> and should no longer be used. They are documented primarily to help understand older code bases.

<span class="page-not-created">`HTMLTableCellElement.align`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A [`DOMString`](domstring) containing an enumerated value reflecting the [`align`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td#attr-align) attribute. It indicates the alignment of the element's contents with respect to the surrounding context. The possible values are `"left"`, `"right"`, and `"center"`.

<span class="page-not-created">`HTMLTableCellElement.axis`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A [`DOMString`](domstring) containing a name grouping cells in virtual. It reflects the obsolete [`axis`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td#attr-axis) attribute.

<span class="page-not-created">`HTMLTableCellElement.bgColor`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A [`DOMString`](domstring) containing the background color of the cells. It reflects the obsolete [`bgcolor`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td#attr-bgcolor) attribute.

<span class="page-not-created">`HTMLTableCellElement.ch`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A [`DOMString`](domstring) containing one single chararcter. This character is the one to align all the cell of a column on. It reflects the [`char`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td#attr-char) and default to the decimal points associated with the language, e.g. `'.'` for English, or `','` for French. This property was optional and was not very well supported.

<span class="page-not-created">`HTMLTableCellElement.chOff`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A [`DOMString`](domstring) containing a integer indicating how many characters must be left at the right (for left-to-right scripts; or at the left for right-to-left scripts) of the character defined by `HTMLTableCellElement.ch`. This property was optional and was not very well supported.

<span class="page-not-created">`HTMLTableCellElement.height`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A [`DOMString`](domstring) containing a length of pixel of the hinted height of the cell. It reflects the obsolete [`height`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td#attr-height) attribute.

<span class="page-not-created">`HTMLTableCellElement.noWrap`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value reflecting the [`nowrap`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td#attr-nowrap) attribute and indicating if cell content can be broken in several lines.

<span class="page-not-created">`HTMLTableCellElement.vAlign`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A [`DOMString`](domstring) representing an enumerated value indicating how the content of the cell must be vertically aligned. It reflects the [`valign`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td#attr-valign) attribute and can have one of the following values: `"top"`, `"middle"`, `"bottom"`, or `"baseline"`. Use the CSS [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align) property instead.

<span class="page-not-created">`HTMLTableCellElement.width`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A [`DOMString`](domstring) specifying the number of pixels wide the cell should be drawn, if possible. This property reflects the also obsolete [`width`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td#attr-width) attribute. Use the CSS [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) property instead.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/tabular-data.html#htmltablecellelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLTableCellElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/tabular-data.html#htmltablecellelement">HTML5<br />
<span class="small">The definition of 'HTMLTableCellElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The following properties have been obsoleted: <code>align</code>, <code>axis</code>, <code>bgColor</code>, <code>height</code>, <code>width</code>, <code>ch</code>, <code>chOff</code>, <code>noWrap</code>, and <code>vAlign</code>.<br />
The <code>headers</code> property is now read-only and contains a <span class="page-not-created"><code>DOMSettableTokenList</code></span> rather than a mere <a href="domstring"><code>DOMString</code></a>.<br />
The <code>colspan</code> and <code>rowspan</code> properties are now <code>unsigned long</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-82915075">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLTableCellElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>The <code>cellIndex</code> property is now read-only.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-82915075">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLTableCellElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`HTMLTableCellElement`

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

`abbr`

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

`axis`

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

`cellIndex`

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

`colSpan`

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

`headers`

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

`height`

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

`noWrap`

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

`rowSpan`

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

`scope`

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

- The HTML elements implementing this interface: [`<th>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/th) and [`<td>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td) by inheritance via [`HTMLTableHeaderCellElement`](htmltablecellelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> and [`HTMLTableDataCellElement`](htmltablecellelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableCellElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableCellElement</a>
