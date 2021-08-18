# HTMLLegendElement

The `HTMLLegendElement` is an interface allowing to access properties of the [`<legend>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/legend) elements. It inherits properties and methods from the [`HTMLElement`](htmlelement) interface.

## Properties

_Inherits properties from its parent, [`HTMLElement`](htmlelement)._

<span class="page-not-created">`HTMLLegendElement.form`</span> <span class="badge inline readonly">Read only </span>  
Is a [`HTMLFormElement`](htmlformelement) representing the form that this legend belongs to. If the legend has a fieldset element as its parent, then this attribute returns the same value as the **form** attribute on the parent fieldset element. Otherwise, it returns null.

<span class="page-not-created">`HTMLLegendElement.accessKey`</span>  
Is a [`DOMString`](domstring) representing a single-character access key to give access to the element.

<span class="page-not-created">`HTMLLegendElement.align`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) representing the alignment relative to the form set

## Methods

_No specific method; inherits methods from its parent, [`HTMLElement`](htmlelement)._

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmllegendelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLLegendElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/forms.html#the-legend-element">HTML 5.1<br />
<span class="small">The definition of 'HTMLLegendElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/forms.html#the-legend-element">HTML5<br />
<span class="small">The definition of 'HTMLLegendElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The property <code>accessKey</code> is now defined on <a href="htmlelement"><code>HTMLElement</code></a>.<br />
The following property is now obsolete: <code>align</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-21482039">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLLegendElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-21482039">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLLegendElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`HTMLLegendElement`

1

12

1

6

≤12.1

1

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

6

≤12.1

1

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

6

≤12.1

1

1

18

4

≤12.1

1

1.0

## See also

- The HTML element implementing this interface: [`<legend>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/legend)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLLegendElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLLegendElement</a>
