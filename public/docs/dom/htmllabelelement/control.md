# HTMLLabelElement.control

The read-only `HTMLLabelElement.control` property returns a reference to the control (in the form of an object of type [`HTMLElement`](../htmlelement) or one of its derivatives) with which the [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label) element is associated, or `null` if the label isn't associated with a control.

## Syntax

    control = HTMLLabelElement.control

### Value

An [`HTMLElement`](../htmlelement) derived object representing the control with which the [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label) is associated, or `null` if the label stands alone.

If this property has a value and [`HTMLLabelElement.htmlFor`](htmlfor) has a value, the [`HTMLLabelElement.htmlFor`](htmlfor) property must refer to the same control.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#dom-label-control">HTML Living Standard<br />
<span class="small">The definition of 'control' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

## See also

- [`HTMLLabelElement`](../htmllabelelement)
- [`HTMLElement`](../htmlelement)
- [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label)
- [HTML forms guide](https://developer.mozilla.org/en-US/docs/Learn/Forms)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLLabelElement/control" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLLabelElement/control</a>
