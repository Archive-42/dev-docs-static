HTMLElement.isContentEditable
=============================

The `HTMLElement.isContentEditable` read-only property returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the contents of the element are editable; otherwise it returns `false`.

Syntax
------

    editable = element.isContentEditable

Example
-------

### HTML

    <p id="myText1">Uneditable Paragraph</p>
    <p id="myText2" contentEditable="true">Editable Paragraph</p>

    <p id="infoText1">Can edit the first paragraph? </p>
    <p id="infoText2">Can edit the second paragraph? </p>

### JavaScript

    document.getElementById('infoText1').innerHTML += document.getElementById('myText1').isContentEditable;
    document.getElementById('infoText2').innerHTML += document.getElementById('myText2').isContentEditable;

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/editing.html#dom-iscontenteditable">HTML Living Standard<br />
<span class="small">The definition of 'HTMLElement.contenteditable' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from latest snapshot, <a href="https://www.w3.org/TR/html51/">HTML 5.1</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/editing.html#dom-iscontenteditable">HTML 5.1<br />
<span class="small">The definition of 'HTMLElement.contenteditable' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>, no change from <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/editing.html#dom-iscontenteditable">HTML5<br />
<span class="small">The definition of 'HTMLElement.contenteditable' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>, initial definition.</td></tr></tbody></table>

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

`isContentEditable`

1

12

4

5.5

≤12.1

3

4.4

18

4

≤12.1

1

1.0

See also
--------

-   [`HTMLElement/contentEditable`](contenteditable)
-   The [`contenteditable`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-contenteditable) global attribute.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/isContentEditable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/isContentEditable</a>
