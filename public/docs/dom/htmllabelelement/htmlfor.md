# HTMLLabelElement.htmlFor

The `HTMLLabelElement.htmlFor` property reflects the value of the [`for`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label#attr-for) content property. That means that this script-accessible property is used to set and read the value of the content property `for`, which is the ID of the label's associated control element.

## Syntax

    controlId = HTMLLabelElement.htmlFor

    HTMLLabelElement.htmlFor = newId

### Value

A [`DOMString`](../domstring) which contains the ID string of the element which is associated with the control.

If this property has a value, the [`HTMLLabelElement.control`](control) property must refer to the same control.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-label-htmlfor">HTML Living Standard<br />
<span class="small">The definition of 'htmlFor' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

- [`HTMLLabelElement`](../htmllabelelement)
- [`HTMLLabelElement.control`](control)
- [`HTMLElement`](../htmlelement)
- [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label)
- [HTML forms guide](https://developer.mozilla.org/en-US/docs/Learn/Forms)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLLabelElement/htmlFor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLLabelElement/htmlFor</a>
