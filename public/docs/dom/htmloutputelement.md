HTMLOutputElement
=================

The `HTMLOutputElement` interface provides properties and methods (beyond those inherited from [`HTMLElement`](htmlelement)) for manipulating the layout and presentation of [`<output>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/output) elements.

Properties
----------

*This interface also inherits properties from its parent, [`HTMLElement`](htmlelement).*

<span class="page-not-created">`HTMLOutputElement.defaultValue`</span>  
A [`DOMString`](domstring) representing the default value of the element, initially the empty string.

 <span class="page-not-created">`HTMLOutputElement.form`</span><span class="badge inline readonly">Read only </span>   
An [`HTMLFormElement`](htmlformelement) indicating the form associated with the control, reflecting the [`form`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/output#attr-form) HTML attribute if it is defined.

 <span class="page-not-created">`HTMLOutputElement.htmlFor`</span><span class="badge inline readonly">Read only </span>   
A [`DOMTokenList`](domtokenlist) reflecting the [`for`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/output#attr-for) HTML attribute, containing a list of IDs of other elements in the same document that contribute to (or otherwise affect) the calculated `value`.

 [`HTMLOutputElement.labels`](htmloutputelement/labels)<span class="badge inline readonly">Read only </span>   
A [`NodeList`](nodelist) of [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label) elements associated with the element.

<span class="page-not-created">`HTMLOutputElement.name`</span>  
A [`DOMString`](domstring) reflecting the [`name`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/output#attr-name) HTML attribute, containing the name for the control that is submitted with form data.

 <span class="page-not-created">`HTMLOutputElement.type`</span><span class="badge inline readonly">Read only </span>   
The [`DOMString`](domstring) "`output`".

 <span class="page-not-created">`HTMLOutputElement.validationMessage`</span><span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) representing a localized message that describes the validation constraints that the control does not satisfy (if any). This is the empty string if the control is not a candidate for constraint validation (`willValidate` is `false`), or it satisfies its constraints.

 <span class="page-not-created">`HTMLOutputElement.validity`</span><span class="badge inline readonly">Read only </span>   
A [`ValidityState`](validitystate) representing the validity states that this element is in.

<span class="page-not-created">`HTMLOutputElement.value`</span>  
A [`DOMString`](domstring) representing the value of the contents of the elements. Behaves like the [`Node.textContent`](node/textcontent) property.

 <span class="page-not-created">`HTMLOutputElement.willValidate`</span><span class="badge inline readonly">Read only </span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the element is a candidate for constraint validation.

Methods
-------

*This interface also inherits methods from its parent, [`HTMLElement`](htmlelement).*

<span class="page-not-created">`HTMLOutputElement.checkValidity()`</span>  
Checks the validity of the element and returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) holding the check result.

<span class="page-not-created">`HTMLOutputElement.reportValidity()`</span>  
This method reports the problems with the constraints on the element, if any, to the user. If there are problems, fires an [`invalid`](htmlinputelement/invalid_event) event at the element, and returns `false`; if there are no problems, it returns `true`.

When the problem is reported, the user agent may focus the element and change the scrolling position of the document or perform some other action that brings the element to the user's attention. User agents may report more than one constraint violation if this element suffers from multiple problems at once. If the element is not rendered, then the user agent may report the error for the running script instead of notifying the user.

<span class="page-not-created">`HTMLOutputElement.setCustomValidity()`</span>  
Sets a custom validity message for the element. If this message is not the empty string, then the element is suffering from a custom validity error, and does not validate.

Modes
-----

This element behaves in one of two modes: *default* mode and *value* mode.

### Default mode

Initially, the element is in default mode, and so the contents of the element represent both the value of the element and its default value.

If the element is in default mode when the descendants of the element are changed in any way, the `defaultValue` property is set to the value of the [`textContent`](node/textcontent) property.

Resetting the form puts the element into default mode, and sets the [`textContent`](node/textcontent) property to the value of the `defaultValue` property.

### Value mode

The element goes into value mode when the contents of the `value` property are set. The `value` property otherwise behaves like the [`textContent`](node/textcontent) property. When the element is in value mode, the default value is accessible only through the `defaultValue` property.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmloutputelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLOutputElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/forms.html#the-output-element">HTML 5.1<br />
<span class="small">The definition of 'HTMLOutputElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/forms.html#the-output-element">HTML5<br />
<span class="small">The definition of 'HTMLOutputElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`HTMLOutputElement`

9

14

4

No

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

`checkValidity`

9

14

4

No

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

`defaultValue`

9

14

4

No

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

`form`

9

14

4

No

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

`htmlFor`

9

Before Chrome 50, this property returned the deprecated child `DOMSettableTokenList` instead of `DOMTokenList`.

14

4

No

15

Before Opera 37, this property returned the deprecated child `DOMSettableTokenList` instead of `DOMTokenList`.

5.1

≤37

Before Chrome 50, this property returned the deprecated child `DOMSettableTokenList` instead of `DOMTokenList`.

18

Before Chrome 50, this property returned the deprecated child `DOMSettableTokenList` instead of `DOMTokenList`.

4

14

Before Opera 37, this property returned the deprecated child `DOMSettableTokenList` instead of `DOMTokenList`.

5

1.0

Before Samsung Internet 5.0, this property returned the deprecated child `DOMSettableTokenList` instead of `DOMTokenList`.

`labels`

9

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

9

14

4

No

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

`reportValidity`

40

14

49

No

27

10.1

40

40

49

27

10.3

4.0

`setCustomValidity`

9

14

4

No

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

`type`

9

14

4

No

15

5.1

≤37

18

4

14

5

1.0

`validationMessage`

9

14

4

No

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

`validity`

9

14

4

No

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

`value`

9

14

4

No

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

`willValidate`

9

14

4

No

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

See also
--------

-   The HTML element implementing this interface: [`<output>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/output).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLOutputElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLOutputElement</a>
