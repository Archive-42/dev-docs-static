SubmitEvent()
=============

The `SubmitEvent()` constructor creates and returns a new [`SubmitEvent`](../submitevent) object, which is used to represent a [`submit`](../htmlformelement/submit_event) event fired at an [HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML) [form](https://developer.mozilla.org/en-US/docs/Learn/Forms).

Syntax
------

    let submitEvent = new SubmitEvent(type,eventInitDict);

### Parameters

`type`  
A [`DOMString`](../domstring) indicating the event which occurred. For `SubmitEvent`, this is always `submit`.

 `eventInitDict` <span class="badge inline optional">Optional</span>   
An optional dictionary of initial values for the event's properties.

### Return value

A [`SubmitEvent`](../submitevent) object configured using the given inputs.

Examples
--------

This code snippet locates a form in the current document, and then an HTML [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) within the form with the class `submit` on it. Next, a new [`SubmitEvent`](../submitevent) is created, configured with its [`submitter`](submitter) set to the identified button (or `null` if the button wasn't found). Then the event is sent to the form, telling the form that it's been submitted by the button.

    const form = document.querySelector("form");
    const formTrigger = form.querySelector("button.submit");
    const submitEvent = new SubmitEvent("submit", { submitter: formTrigger });

    form.dispatchEvent(submitEvent);

This is a somewhat contrived example, as you can do nearly all of this much more easily, but this gives you deep control over the process that can be useful.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/form-control-infrastructure.html#submitevent">HTML Living Standard<br />
<span class="small">The definition of 'SubmitEvent()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`SubmitEvent`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SubmitEvent/SubmitEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SubmitEvent/SubmitEvent</a>
