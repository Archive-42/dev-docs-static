# HTMLFormElement.length

The `HTMLFormElement.length` read-only property returns the number of controls in the [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) element. You can access the list of the form's controls using the [`elements`](elements) property.

This includes both elements that are descendants of the `<form>` element as well as elements that are made members of the form using their `form` property.

{{page("/en-US/docs/Web/API/HTMLFormElement", "Elements that are considered form controls")}}

## Syntax

    numControls = form.length;

### Value

`numControls` is the number of form controls within the `<form>`. This is the same as the number of the elements in the [`HTMLFormControlsCollection`](../htmlformcontrolscollection) returned by the [`elements`](elements) property.

## Example

    if (document.getElementById('form1').length > 1) {
      // more than one form control here
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-form-length">HTML Living Standard<br />
<span class="small">The definition of 'HTMLFormElement: length' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`length`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/length" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/length</a>
