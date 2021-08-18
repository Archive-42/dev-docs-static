# HTMLParamElement

The `HTMLParamElement` interface provides special properties (beyond those of the regular [`HTMLElement`](htmlelement) object interface it inherits) for manipulating [`<param>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/param) elements, representing a pair of a key and a value that acts as a parameter for an [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object) element.

## Properties

_Inherits properties from its parent, [`HTMLElement`](htmlelement)._

<span class="page-not-created">`HTMLParamElement.name`</span>  
Is a [`DOMString`](domstring) representing the name of the parameter. It reflects the [`name`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/param#attr-name) attribute.

<span class="page-not-created">`HTMLParamElement.value`</span>  
Is a [`DOMString`](domstring) representing the value associated to the parameter. It reflects the [`value`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/param#attr-value) attribute.

<span class="page-not-created">`HTMLParamElement.type`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) containing the type of the parameter when `valueType` has the `"ref"` value. It reflects the [`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/param#attr-type) attribute.

<span class="page-not-created">`HTMLParamElement.valueType`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`DOMString`](domstring) containing the type of the `value`. It reflects the [`valuetype`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/param#attr-%3ccode%3evaluetype%3c/code%3e) attribute and has one of the values: `"data"`, `"ref"`, or `"object"`.

## Methods

_No specific methods, inherits methods from its parent, [`HTMLElement`](htmlelement)._

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlparamelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLParamElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#the-param-element">HTML5<br />
<span class="small">The definition of 'HTMLParamElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The following properties are now obsolete: <code>type</code>, and <code>valueType</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-64077273">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLParamElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-64077273">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLParamElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`HTMLParamElement`

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

`type`

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

`value`

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

`valueType`

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

## See also

- The HTML element implementing this interface: [`<param>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/param).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLParamElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLParamElement</a>
