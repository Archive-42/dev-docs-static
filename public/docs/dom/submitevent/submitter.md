SubmitEvent.submitter
=====================

The read-only `submitter` property found on the [`SubmitEvent`](../submitevent) interface specifies the submit button or other element that was invoked to cause the form to be submitted.

Syntax
------

    let submitter = submitEvent.submitter;

### Value

An element, indicating the element that sent the [`submit`](../htmlformelement/submit_event) event to the form. While this is often an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element whose <span class="page-not-created">`type`</span> or a [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) whose <span class="page-not-created">`type`</span> is `submit`, it could be some other element which has initiated a submission process.

If the submission was not triggered by a button of some kind, the value of `submitter` is `null`.

Examples
--------

In this example, a shopping cart may have an assortment of different submit buttons depending on factors such as the user's settings, the shop's settings, and any minimum or maximum shopping card totals established by the payment processors. Each of the submit elements' [`id`](../element/id) is used to identify which payment processor the button corresponds to.

    let form = document.querySelector("form");
    form.addEventListener("submit", (event) => {
      let submitter = event.submitter;
      let handler = submitter.id;

      if (handler) {
        processOrder(form, handler);
      } else {
        showAlertMessage("An unknown or unaccepted payment type was selected. Please try again.", "OK");
      }
    });

The handler ID is obtained by using the `submit` event's [`submitter`](submitter) property to get the submit button, from which we then get the ID. With that in hand, we can call a `processOrder()` function to handle the order, passing along the form and the handler ID.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/form-control-infrastructure.html#dom-submitevent-submitter">HTML Living Standard<br />
<span class="small">The definition of 'SubmitEvent.submitter' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

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

`submitter`

81

?

75

No

?

No

81

81

?

?

No

13.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SubmitEvent/submitter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SubmitEvent/submitter</a>
