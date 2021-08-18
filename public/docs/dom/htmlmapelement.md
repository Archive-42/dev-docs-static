# HTMLMapElement

The `HTMLMapElement` interface provides special properties and methods (beyond those of the regular object [`HTMLElement`](htmlelement) interface it also has available to it by inheritance) for manipulating the layout and presentation of map elements.

## Properties

_Inherits properties from its parent, [`HTMLElement`](htmlelement)._

<span class="page-not-created">`HTMLMapElement.name`</span>  
Is a [`DOMString`](domstring) representing the [`<map>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/map) element for referencing it other context. If the `id` attribute is set, this must have the same value; and it cannot be `null` or empty.

<span class="page-not-created">`HTMLMapElement.areas`</span> <span class="badge inline readonly">Read only </span>  
Is a live [`HTMLCollection`](htmlcollection) representing the [`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area) elements associated to this [`<map>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/map).

## Methods

_No specific method; inherits methods from its parent, [`HTMLElement`](htmlelement) ._

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlmapelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMapElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#the-map-element">HTML5<br />
<span class="small">The definition of 'HTMLMapElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Adds the <code>images</code> property.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-94109203">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLAreaElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-94109203">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLAreaElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`HTMLMapElement`

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

`areas`

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

## See also

- HTML element implementing this interface: [`<map>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/map).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMapElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMapElement</a>
