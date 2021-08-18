# HTMLElement.contentEditable

The `contentEditable` property of the [`HTMLElement`](../htmlelement) interface specifies whether or not the element is editable. This enumerated attribute can have the following values:

- '`true`' indicates that the element is `contenteditable`.
- '`false`' indicates that the element cannot be edited.
- '`inherit`' indicates that the element inherits its parent's editable status.

You can use the [`HTMLElement.isContentEditable`](iscontenteditable) property to test the computed [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value of this property.

## Syntax

    editable = element.contentEditable
    element.contentEditable = 'true'

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#contenteditable">HTML Living Standard<br />
<span class="small">The definition of 'contenteditable' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`contentEditable`

1

12

3

5.5

9

3

4.4

18

4

10.1

1

1.0

In Internet Explorer, `contenteditable` cannot be applied to the [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table), [`<col>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/col), [`<colgroup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/colgroup), [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody), [`<td>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td), [`<tfoot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tfoot), [`<th>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/th), [`<thead>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/thead), and [`<tr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr) elements directly. A content editable [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) or [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) element can be placed inside the individual table cells.

## See also

- [Making content editable](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Editable_content)
- [`HTMLElement.isContentEditable`](iscontenteditable)
- The [`contenteditable`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-contenteditable) global attribute.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/contentEditable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/contentEditable</a>
