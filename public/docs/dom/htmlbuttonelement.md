HTMLButtonElement
=================

The `HTMLButtonElement` interface provides properties and methods (beyond the regular [`HTMLElement`](htmlelement) interface it also has available to it by inheritance) for manipulating [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) elements.

Properties
----------

*Inherits properties from its parent, [`HTMLElement`](htmlelement).*

<span class="page-not-created">`HTMLButtonElement.accessKey`</span>  
Is a [`DOMString`](domstring) indicating the single-character keyboard key to give access to the button.

<span class="page-not-created">`HTMLButtonElement.autofocus`</span>  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether or not the control should have input focus when the page loads, unless the user overrides it, for example by typing in a different control. Only one form-associated element in a document can have this attribute specified.

[`HTMLButtonElement.disabled`](htmlbuttonelement/disabled)  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether or not the control is disabled, meaning that it does not accept any clicks.

 <span class="page-not-created">`HTMLButtonElement.form`</span> <span class="badge inline readonly">Read only </span>   
Is a [`HTMLFormElement`](htmlformelement) reflecting the form that this button is associated with. If the button is a descendant of a form element, then this attribute is the ID of that form element.  
If the button is not a descendant of a form element, then the attribute can be the ID of any form element in the same document it is related to, or the `null` value if none matches.

<span class="page-not-created">`HTMLButtonElement.formAction`</span>  
Is a [`DOMString`](domstring) reflecting the URI of a resource that processes information submitted by the button. If specified, this attribute overrides the [`action`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-action) attribute of the [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) element that owns this element.

<span class="page-not-created">`HTMLButtonElement.formEnctype`</span>  
Is a [`DOMString`](domstring) reflecting the type of content that is used to submit the form to the server. If specified, this attribute overrides the [`enctype`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-enctype) attribute of the [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) element that owns this element.

<span class="page-not-created">`HTMLButtonElement.formMethod`</span>  
Is a [`DOMString`](domstring) reflecting the HTTP method that the browser uses to submit the form. If specified, this attribute overrides the [`method`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-method) attribute of the [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) element that owns this element.

<span class="page-not-created">`HTMLButtonElement.formNoValidate`</span>  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating that the form is not to be validated when it is submitted. If specified, this attribute overrides the [`novalidate`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-novalidate) attribute of the [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) element that owns this element.

<span class="page-not-created">`HTMLButtonElement.formTarget`</span>  
Is a [`DOMString`](domstring) reflecting a name or keyword indicating where to display the response that is received after submitting the form. If specified, this attribute overrides the [`target`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#attr-target) attribute of the [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) element that owns this element.

 [`HTMLButtonElement.labels`](htmlbuttonelement/labels) <span class="badge inline readonly">Read only </span>   
Is a [`NodeList`](nodelist) that represents a list of [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label) elements that are labels for this button.

 <span class="page-not-created">`HTMLButtonElement.menu`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Is a [`HTMLMenuElement`](htmlmenuelement) representing the menu element to be displayed if the button is clicked and is of `type="menu"`.

<span class="page-not-created">`HTMLButtonElement.name`</span>  
Is a [`DOMString`](domstring) representing the name of the object when submitted with a form. If specified, it must not be the empty string.

<span class="page-not-created">`HTMLButtonElement.tabIndex`</span>  
Is a `long` that represents this element's position in the tabbing order.

<span class="page-not-created">`HTMLButtonElement.type`</span>  
Is a [`DOMString`](domstring) indicating the behavior of the button. This is an enumerated attribute with the following possible values:

-   `submit`: The button submits the form. This is the default value if the attribute is not specified, or if it is dynamically changed to an empty or invalid value.
-   `reset`: The button resets the form.
-   `button`: The button does nothing.
-   `menu`: The button displays a menu. <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

 <span class="page-not-created">`HTMLButtonElement.willValidate`</span> <span class="badge inline readonly">Read only </span>   
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the button is a candidate for constraint validation. It is `false` if any conditions bar it from constraint validation, including: its `type` property is `reset` or `button`; it has a [`<datalist>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/datalist) ancestor; or the `disabled` property is set to `true`.

 <span class="page-not-created">`HTMLButtonElement.validationMessage`</span> <span class="badge inline readonly">Read only </span>   
Is a [`DOMString`](domstring) representing the localized message that describes the validation constraints that the control does not satisfy (if any). This attribute is the empty string if the control is not a candidate for constraint validation (`willValidate` is `false`), or it satisfies its constraints.

 <span class="page-not-created">`HTMLButtonElement.validity`</span> <span class="badge inline readonly">Read only </span>   
Is a [`ValidityState`](validitystate) representing the validity states that this button is in.

<span class="page-not-created">`HTMLButtonElement.value`</span>  
Is a [`DOMString`](domstring) representing the current form control value of the button.

Methods
-------

*Inherits methods from its parent, [`HTMLElement`](htmlelement)*

<table><thead><tr class="header"><th>Name</th><th>Return Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>checkValidity()</code></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean"><code>Boolean</code></a></td><td>Not supported for reset or button elements.</td></tr><tr class="even"><td><code>reportValidity()</code></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean"><code>Boolean</code></a></td><td>Not supported for reset or button elements.</td></tr><tr class="odd"><td><code>setCustomValidity(in DOMString error)</code></td><td><code>void</code></td><td>Not supported for reset or button elements.</td></tr></tbody></table>

With Gecko-based browser, use the [`:-moz-submit-invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:-moz-submit-invalid) pseudo-class to style submit buttons based on the validation of a form.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlbuttonelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLButtonElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/sec-forms.html#htmlbuttonelement">HTML 5.2<br />
<span class="small">The definition of 'HTMLButtonElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The <code>menu</code> attribute and <code>type="menu"</code> value have been removed.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html51/sec-forms.html#htmlbuttonelement-htmlbuttonelement">HTML 5.1<br />
<span class="small">The definition of 'HTMLButtonElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The following attribute has been added: <code>menu</code>.<br />
The <code>type</code> attribute can take one more value, "<code>menu</code>".</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#the-button-element">HTML5<br />
<span class="small">The definition of 'HTMLButtonElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The attributes <code>tabindex</code> and <code>accesskey</code>, are now defined on <a href="htmlelement"><code>HTMLElement</code></a>.<br />
The following attributes have been added: <code>autofocus</code>, <code>formAction</code>, <code>formEnctype</code>, <code>formMethod</code>, <code>formNoValidate</code>, <code>formTarget</code>, <code>labels</code>, <code>validity</code>, <code>validationMessage</code>, and <code>willValidate</code>.<br />
The following methods have been added: <code>checkValidity()</code>, <code>setCustomValidity()</code>.<br />
The <code>type</code> attribute is no more read-only.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-34812697">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLButtonElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-34812697">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLButtonElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`HTMLButtonElement`

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

`autofocus`

1

12

1

10

≤12.1

4

1

18

4

≤12.1

3.2

1.0

`checkValidity`

4

12

4

10

≤12.1

5

≤37

18

4

≤12.1

5

1.0

`disabled`

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

`form`

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

`formAction`

9

12

4

In Firefox 56, the implementation has been updated so that the `formAction` property returns the correct form submission URL, as per spec, when the associated button is being used to submit a form ([bug 1366361](https://bugzil.la/1366361)).

10

≤12.1

5.1

≤37

18

4

In Firefox 56, the implementation has been updated so that the `formAction` property returns the correct form submission URL, as per spec, when the associated button is being used to submit a form ([bug 1366361](https://bugzil.la/1366361)).

≤12.1

5

1.0

`formEnctype`

9

12

4

10

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

`formMethod`

9

12

4

10

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

`formNoValidate`

4

12

4

10

≤12.1

5

≤37

18

4

≤12.1

4

1.0

`formTarget`

9

12

4

10

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

`labels`

6

18

56

No

≤12.1

5.1

≤37

18

56

≤12.1

5

1.0

`name`

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

`reportValidity`

40

17

49

No

27

10.1

40

40

64

27

10.3

4.0

`setCustomValidity`

4

12

4

10

≤12.1

5

≤37

18

4

≤12.1

5

1.0

`type`

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

`validationMessage`

5

12

4

10

≤12.1

5

≤37

18

4

≤12.1

4

1.0

`validity`

3

12

4

10

≤12.1

5

≤37

18

4

≤12.1

4

1.0

`value`

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

`willValidate`

1

12

4

10

≤12.1

4

1

18

4

≤12.1

3

1.0

See also
--------

-   HTML element implementing this interface: [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLButtonElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLButtonElement</a>
