contenteditable
===============

The `contenteditable` [global attribute](../global_attributes) is an enumerated attribute indicating if the element should be editable by the user. If so, the browser modifies its widget to allow editing.

The attribute must take one of the following values:

-   `true` or an *empty string*, which indicates that the element is editable.
-   `false`, which indicates that the element is not editable.

If the attribute is given without a value, like `<label contenteditable>Example Label</label>`, its value is treated as an empty string.

If this attribute is missing or its value is invalid, its value is *inherited* from its parent element: so the element is editable if its parent is editable.

Note that although its allowed values include `true` and `false`, this attribute is an *enumerated* one and not a *Boolean* one.

You can set the color used to draw the text insertion [caret](https://developer.mozilla.org/en-US/docs/Glossary/caret) with the CSS [`caret-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/caret-color) property.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/editing.html#attr-contenteditable">HTML Living Standard<br />
<span class="small">The definition of 'contenteditable' in that specification.</span></a></td></tr></tbody></table>

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

`contenteditable`

Yes

12

3

5.5

9

Yes

Yes

Yes

4

Yes

Yes

Yes

`caret`

Yes

≤79

No

No

Yes

No

Yes

Yes

No

Yes

No

Yes

`events`

Yes

≤79

No

No

Yes

No

Yes

Yes

No

Yes

No

Yes

`plaintext-only`

Yes

≤79

No

No

Yes

Yes

Yes

Yes

No

Yes

Yes

Yes

`typing`

Yes

≤79

No

No

Yes

No

Yes

Yes

No

Yes

No

Yes

See also
--------

-   [Making content editable](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Editable_content)
-   All [global attributes](../global_attributes)
-   [`HTMLElement.contentEditable`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/contentEditable) and [`HTMLElement.isContentEditable`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/isContentEditable)
-   The CSS [`caret-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/caret-color) property
-   [`HTMLElement` `input` event](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/contenteditable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/contenteditable</a>
