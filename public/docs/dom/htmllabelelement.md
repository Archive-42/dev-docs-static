# HTMLLabelElement

The `HTMLLabelElement` interface gives access to properties specific to [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label) elements. It inherits methods and properties from the base [`HTMLElement`](htmlelement) interface.

## Properties

_Inherits properties from its parent, [`HTMLElement`](htmlelement)._

[`HTMLLabelElement.control`](htmllabelelement/control) <span class="badge inline readonly">Read only </span>  
Is a [`HTMLElement`](htmlelement) representing the control with which the label is associated.

[`HTMLLabelElement.form`](htmllabelelement/form) <span class="badge inline readonly">Read only </span>  
Is a [`HTMLFormElement`](htmlformelement) object representing the form with which the labeled control is associated, or `null` if there is no associated control, or if that control isn't associated with a form. In other words, this is just a shortcut for `HTMLLabelElement.control.form`.

[`HTMLLabelElement.htmlFor`](htmllabelelement/htmlfor)  
Is a string containing the ID of the labeled control. This reflects the [`for`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label#attr-for) attribute.

## Methods

_No specific methods; inherits methods from its parent, [`HTMLElement`](htmlelement)._

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmllabelelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLLabelElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#the-label-element">HTML5<br />
<span class="small">The definition of 'HTMLLabelElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The property <code>accessKey</code> is now defined on <a href="htmlelement"><code>HTMLElement</code></a>.<br />
The following property has been added: <code>control</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-13691394">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLLabelElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-13691394">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLLabelElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`HTMLLabelElement`

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

`control`

6

18

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

`htmlFor`

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

- The HTML element implementing this interface: [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label)
- [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)
- [`HTMLFormElement`](htmlformelement)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLLabelElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLLabelElement</a>
