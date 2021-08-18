HTMLFieldSetElement
===================

The `HTMLFieldSetElement` interface provides special properties and methods (beyond the regular [`HTMLElement`](htmlelement) interface it also has available to it by inheritance) for manipulating the layout and presentation of [`<fieldset>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset) elements.

Properties
----------

*Inherits properties from its parent, [`HTMLElement`](htmlelement).*

<span class="page-not-created">`HTMLFieldSetElement.disabled`</span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) reflecting the [`disabled`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset#attr-disabled) HTML attribute, indicating whether the user can interact with the control.

 <span class="page-not-created">`HTMLFieldSetElement.elements`</span><span class="badge inline readonly">Read only </span>   
The elements belonging to this field set. The type of this property depends on the version of the spec that is implemented by the browser.

 <span class="page-not-created">`HTMLFieldSetElement.form`</span><span class="badge inline readonly">Read only </span>   
An [`HTMLFormControlsCollection`](htmlformcontrolscollection) or [`HTMLCollection`](htmlcollection) referencing the containing form element, if this element is in a form.  
If the field set is not a descendant of a form element, then the attribute can be the ID of any form element in the same document it is related to, or the `null` value if none matches.

<span class="page-not-created">`HTMLFieldSetElement.name`</span>  
A [`DOMString`](domstring) reflecting the [`name`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset#attr-name) HTML attribute, containing the name of the field set. This can be used when accessing the field set in JavaScript. It is *not* part of the data which is sent to the server.

 <span class="page-not-created">`HTMLFieldSetElement.type`</span><span class="badge inline readonly">Read only </span>   
The [`DOMString`](domstring) "`fieldset`".

<span class="page-not-created">`HTMLFieldSetElement.validationMessage`</span>  
A [`DOMString`](domstring) representing a localized message that describes the validation constraints that the element does not satisfy (if any). This is the empty string if the element is not a candidate for constraint validation (`willValidate` is `false`), or it satisfies its constraints.

<span class="page-not-created">`HTMLFieldSetElement.validity`</span>  
A [`ValidityState`](validitystate) representing the validity states that this element is in.

<span class="page-not-created">`HTMLFieldSetElement.willValidate`</span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) `false`, because [`<fieldset>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset) objects are never candidates for constraint validation.

Methods
-------

*Inherits methods from its parent, [`HTMLElement`](htmlelement).*

<span class="page-not-created">`HTMLFieldSetElement.checkValidity()`</span>  
Always returns `true` because [`<fieldset>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset) objects are never candidates for constraint validation.

<span class="page-not-created">`HTMLFieldSetElement.reportValidity()`</span>  
Always returns `true` because [`<fieldset>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset) objects are never candidates for constraint validation.

<span class="page-not-created">`HTMLFieldSetElement.setCustomValidity()`</span>  
Sets a custom validity message for the field set. If this message is not the empty string, then the field set is suffering from a custom validity error, and does not validate.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlfieldsetelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLFieldSetElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/forms.html#the-fieldset-element">HTML 5.1<br />
<span class="small">The definition of 'HTMLFieldSetElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/forms.html#the-fieldset-element">HTML5<br />
<span class="small">The definition of 'HTMLFieldSetElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The following properties have been added: <code>disabled</code>, <code>elements</code>, <code>name</code>, <code>type</code>, <code>valdiationMessage</code>, <code>validity</code>, and <code>willValidate</code>.<br />
The following methods have been added: <code>checkValidity()</code>, <code>setCustomValidity()</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-7365882">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLFieldSetElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-7365882">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLFieldSetElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`HTMLFieldSetElement`

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

20

12

1

5.5

≤12.1

6

≤37

25

4

≤12.1

6

1.5

`elements`

21

17

4

No

≤12.1

6.1

≤37

25

4

≤12.1

7

1.0

`form`

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

`name`

19

14

1

No

15

6

≤37

25

4

14

6

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

19

17

4

No

15

6

≤37

25

4

14

6

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

-   The HTML element implementing this interface: [`<fieldset>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFieldSetElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLFieldSetElement</a>
