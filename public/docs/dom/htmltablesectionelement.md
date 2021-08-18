# HTMLTableSectionElement

The `HTMLTableSectionElement` interface provides special properties and methods (beyond the [`HTMLElement`](htmlelement) interface it also has available to it by inheritance) for manipulating the layout and presentation of sections, that is headers, footers and bodies, in an HTML table.

## Properties

_Inherits properties from its parent, [`HTMLElement`](htmlelement)._

<span class="page-not-created">`HTMLTableSectionElement.align`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) containing an enumerated value reflecting the [`align`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr#attr-align) attribute. It indicates the alignment of the element's contents with respect to the surrounding context. The possible values are `"left"`, `"right"`, and `"center"`.

<span class="page-not-created">`HTMLTableSectionElement.rows`</span> <span class="badge inline readonly">Read only </span>  
Returns a live [`HTMLCollection`](htmlcollection) containing the rows in the section. The `HTMLCollection` is live and is automatically updated when rows are added or removed.

<span class="page-not-created">`HTMLTableSectionElement.ch`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) containing one single chararcter. This character is the one to align all the cell of a column on. It reflects the [`char`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr#attr-char) and default to the decimal points associated with the language, e.g. `'.'` for English, or `','` for French. This property was optional and was not very well supported.

<span class="page-not-created">`HTMLTableSectionElement.chOff`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) containing a integer indicating how many characters must be left at the right (for left-to-right scripts; or at the left for right-to-left scripts) of the character defined by `HTMLTableRowElement.ch`. This property was optional and was not very well supported.

<span class="page-not-created">`HTMLTableSectionElement.vAlign`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) representing an enumerated value indicating how the content of the cell must be vertically aligned. It reflects the [`valign`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr#attr-valign) attribute and can have one of the following values: `"top"`, `"middle"`, `"bottom"`, or `"baseline"`.

## Methods

_Inherits methods from its parent, [`HTMLElement`](htmlelement)_.

<span class="page-not-created">`HTMLTableSectionElement.deleteRow()`</span>  
Removes the row at the given position in the section. If the given position is greater (or equal as it starts at zero) than the amount of rows in the section, or is smaller than `0`, it raises a [`DOMException`](domexception) with the `IndexSizeError` value.

<span class="page-not-created">`HTMLTableSectionElement.insertRow()`</span>  
Inserts a new row just before the given position in the section. If the given position is not given or is `-1`, it appends the row to the end of section. If the given position is greater (or equal as it starts at zero) than the amount of rows in the section, or is smaller than `-1`, it raises a [`DOMException`](domexception) with the `IndexSizeError` value.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/tabular-data.html#htmltablesectionelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLTableSectionElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/tabular-data.html#htmltablesectionelement">HTML5<br />
<span class="small">The definition of 'HTMLTableSectionElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The parameter of <code>insertCell</code> is now optional.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-67417573">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLTableSectionElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>The methods <code>insertRow</code> and <code>deleteRow</code> can raise exceptions.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-67417573">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLTableSectionElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`HTMLTableSectionElement`

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

`insertRow`

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

## See also

- The HTML elements implementing this interface: [`<tfoot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tfoot), [`<thead>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/thead), and [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableSectionElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableSectionElement</a>
