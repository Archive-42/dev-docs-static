# HTMLProgressElement

The `HTMLProgressElement` interface provides special properties and methods (beyond the regular [`HTMLElement`](htmlelement) interface it also has available to it by inheritance) for manipulating the layout and presentation of [`<progress>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/progress) elements.

## Properties

_Inherits properties from its parent, [`HTMLElement`](htmlelement)._

<span class="page-not-created">`HTMLProgressElement.max`</span>  
Is a `double` value reflecting the content attribute of the same name, limited to numbers greater than zero. Its default value is `1.0`.

<span class="page-not-created">`HTMLProgressElement.position`</span><span class="badge inline readonly">Read only </span>  
Returns a `double` value returning the result of dividing the current value (`value`) by the maximum value (`max`); if the progress bar is an indeterminate progress bar, it returns `-1`.

<span class="page-not-created">`HTMLProgressElement.value`</span>  
Is a `double` value that reflects the current value; if the progress bar is an indeterminate progress bar, it returns `0`.

[`HTMLProgressElement.labels`](htmlprogresselement/labels)<span class="badge inline readonly">Read only </span>  
Returns [`NodeList`](nodelist) containing the list of [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label) elements that are labels for this element.

## Methods

_No specific method; inherits properties from its parent, [`HTMLElement`](htmlelement)._

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlprogresselement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLProgressElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/forms.html#the-progress-element">HTML 5.1<br />
<span class="small">The definition of 'HTMLProgressElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/forms.html#the-progress-element">HTML5<br />
<span class="small">The definition of 'HTMLProgressElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`HTMLProgressElement`

6

12

6

10

≤12.1

6

≤37

18

6

≤12.1

6

1.0

`labels`

6

18

56

No

≤12.1

6

≤37

18

56

≤12.1

6

1.0

`max`

6

12

6

10

≤12.1

6

≤37

18

6

≤12.1

6

1.0

`position`

6

12

6

10

≤12.1

6

≤37

18

6

≤12.1

6

1.0

`value`

6

12

6

10

≤12.1

6

≤37

18

6

≤12.1

6

1.0

## See also

- The HTML element implementing this interface: [`<progress>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/progress)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLProgressElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLProgressElement</a>
