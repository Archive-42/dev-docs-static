# HTMLFormElement.requestSubmit()

The [`HTMLFormElement`](../htmlformelement) method `requestSubmit()` requests that the form be submitted using a specific submit button.

## Syntax

    htmlFormElement.requestSubmit(submitter);

### Parameters

`submitter` <span class="badge inline optional">Optional</span>  
The submit button whose attributes describe the method by which the form is to be submitted. This may be either an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) or [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) element whose `type` attribute is `submit`.

If you omit the `submitter` parameter, the form element itself is used as the submitter.

### Return value

None.

### Exceptions

`TypeError`  
The specified `submitter` is not a submit button.

`NotFoundError`  
The specified `submitter` isn't a member of the form on which `requestSubmit()` was called. The submitter must be either a descendant of the form element or must have an [`form`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-form) attribute referring to the form.

## Usage notes

The obvious question is: Why does this method exist, when we've had the [`submit()`](submit) method since the dawn of time?

The answer is simple. `submit()` submits the form, but that's all it does. `requestSubmit()`, on the other hand, acts as if a submit button were clicked. The form's content is validated, and the form is submitted only if validation succeeds. Once the form has been submitted, the [`submit`](submit_event) event is sent back to the form object.

## Examples

In the example below, the form is submitted by attempting to send the request using `requestSubmit()` if it's available. If a submit button with the ID `main-submit` is found, that's used to submit the form. Otherwise, the form is submitted with no `submitter` parameter, so it's submitted directly by the form itself.

If, on the other hand, `requestSubmit()` isn't available, this code falls back to calling the form's [`submit()`](submit) method.

    let myForm = document.querySelector("form");
    let submitButton = myForm.querySelector("#main-submit");

    if (myForm.requestSubmit) {
      if (submitButton) {
        myForm.requestSubmit(submitButton);
      } else {
        myForm.requestSubmit();
      }
    } else {
      myForm.submit();
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-form-requestsubmit">HTML Living Standard<br />
<span class="small">The definition of 'requestSubmit()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`requestSubmit`

76

79

75

No

63

No

76

76

79

54

No

12.0

The compatibility table on this page is generated from structured data. If you'd like to contribute to the data, please check out <https://github.com/mdn/browser-compat-data> and send us a pull request.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/requestSubmit" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/requestSubmit</a>
