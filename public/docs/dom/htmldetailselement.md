# HTMLDetailsElement

The `HTMLDetailsElement` interface provides special properties (beyond the regular [`HTMLElement`](htmlelement) interface it also has available to it by inheritance) for manipulating [`<details>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details) elements.

## Properties

_Inherits properties from its parent, [`HTMLElement`](htmlelement)._

<span class="page-not-created">`HTMLDetailsElement.open`</span>  
Is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) reflecting the [`open`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details#attr-open) HTML attribute, indicating whether or not the element’s contents (not counting the [`<summary>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/summary)) is to be shown to the user.

## Methods

_No specific method; inherits methods from its parent, [`HTMLElement`](htmlelement)._

## Events

Listen to this event using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

`toggle`  
Fired when the `open`/`closed` state of a [`<details>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details) element is toggled.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interactive-elements.html#htmldetailselement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLDetailsElement' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`HTMLDetailsElement`

10

79

49

No

15

6

≤37

18

49

14

6

1.0

`open`

10

79

49

No

15

6

≤37

18

49

14

6

1.0

`toggle_event`

Yes

79

Yes

No

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

## See also

- The HTML element implementing this interface: [`<details>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLDetailsElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLDetailsElement</a>
