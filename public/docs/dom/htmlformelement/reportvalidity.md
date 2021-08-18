# HTMLFormElement.reportValidity()

The `HTMLFormElement.reportValidity()` method returns `true` if the element's child controls satisfy their validation constraints. When `false` is returned, cancelable `invalid` events are fired for each invalid child and validation problems are reported to the user.

## Syntax

    HTMLFormElement.reportValidity()

### Return value

[`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)

## Example

    document.forms['myform'].addEventListener('submit', function() {
      document.forms['myform'].reportValidity();
    }, false);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#dom-cva-reportvalidity">HTML Living Standard<br />
<span class="small">The definition of 'HTMLFormElement.reportValidity()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/semantics.html#the-constraint-validation-api">HTML 5.1<br />
<span class="small">The definition of 'HTMLFormElement.reportValidity()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`reportValidity`

40

17

49

No

27

10.1

40

40

49

27

10.3

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/reportValidity" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/reportValidity</a>
