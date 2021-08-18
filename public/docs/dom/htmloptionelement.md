# HTMLOptionElement

The `HTMLOptionElement` interface represents [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option) elements and inherits all properties and methods of the [`HTMLElement`](htmlelement) interface.

## Properties

_Inherits properties from its parent, [`HTMLElement`](htmlelement)._

<span class="page-not-created">`HTMLOptionElement.defaultSelected`</span>  
Has a value of either `true` or `false` that shows the initial value of the [`selected`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option#attr-selected) HTML attribute, indicating whether the option is selected by default or not.

<span class="page-not-created">`HTMLOptionElement.disabled`</span>  
Has a value of either `true` or `false` representing the value of the [`disabled`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option#attr-disabled) HTML attribute, which indicates that the option is unavailable to be selected. An option can also be disabled if it is a child of an [`<optgroup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/optgroup) element that is disabled.

<span class="page-not-created">`HTMLOptionElement.form`</span> <span class="badge inline readonly">Read only </span>  
Is a [`HTMLFormElement`](htmlformelement) representing the same value as the `form` of the corresponding [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element, if the option is a descendant of a [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element, or null if none is found.

<span class="page-not-created">`HTMLOptionElement.index`</span> <span class="badge inline readonly">Read only </span>  
Is a `long` representing the position of the option within the list of options it belongs to, in tree-order. If the option is not part of a list of options, like when it is part of the [`<datalist>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/datalist) element, the value is `0`.

<span class="page-not-created">`HTMLOptionElement.label`</span> <span class="badge inline readonly">Read only </span>  
Is a [`DOMString`](domstring) that reflects the value of the [`label`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option#attr-label) HTML attribute, which provides a label for the option. If this attribute isn't specifically set, reading it returns the element's text content.

<span class="page-not-created">`HTMLOptionElement.selected`</span>  
Has a value of either `true` or `false` that indicates whether the option is currently selected.

<span class="page-not-created">`HTMLOptionElement.text`</span>  
Is a [`DOMString`](domstring) that contains the text content of the element.

<span class="page-not-created">`HTMLOptionElement.value`</span>  
Is a [`DOMString`](domstring) that reflects the value of the [`value`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option#attr-value) HTML attribute, if it exists; otherwise reflects value of the [`Node.textContent`](node/textcontent) property.

## Methods

_Inherits methods from its parent, [`HTMLElement`](htmlelement)._

Option()  
Is a constructor creating an `HTMLOptionElement` object. It has four values: the text to display, `text`, the value associated, `value`, the value of `defaultSelected`, and the value of `selected`. The last three values are optional.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmloptionelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLOptionElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#the-option-element">HTML5<br />
<span class="small">The definition of 'HTMLOptionElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>A constructor, <code>Option()</code>, has been added.<br />
The <code>form</code> property can be the <code>null</code> value.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-70901257">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLOptionElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>The <code>selected</code> property changed its meaning: it now indicates if the option is currently selected and no longer if it was initially selected.<br />
The <code>defaultSelected</code> property is no longer read-only.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-70901257">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLOptionElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`HTMLOptionElement`

1

12

1

5.5

≤12.1

1.2

1

18

4

≤12.1

1

1.0

`Option`

1

12

1

5.5

≤12.1

1.2

1

18

4

≤12.1

1

1.0

`defaultSelected`

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

`index`

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

`label`

1

12

7

1-7

Prior to Firefox 7 the `label` property incorrectly returned an empty string if not defined instead of returning the element's text content.

6

≤12.1

3

1

18

7

4-7

Prior to Firefox 7 the `label` property incorrectly returned an empty string if not defined instead of returning the element's text content.

≤12.1

1

1.0

`selected`

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

`text`

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

## See also

- The HTML element implementing this interface: [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLOptionElement</a>
