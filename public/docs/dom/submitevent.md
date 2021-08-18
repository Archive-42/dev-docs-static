SubmitEvent
===========

The `SubmitEvent` interface defines the object used to represent an [HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML) form's [`submit`](htmlformelement/submit_event) event. This event is fired at the [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) when the form's submit action is invoked.

Constructor
-----------

[`SubmitEvent()`](submitevent/submitevent)  
Creates and returns a new `SubmitEvent` object whose [`type`](event/type) and other options are configured as specified. Note that currently the only valid `type` for a `SubmitEvent` is `submit`.

Properties
----------

*In addition to the properties listed below, this interface inherits the properties of its parent interface, [`Event`](event).*

 [`submitter`](submitevent/submitter) <span class="badge inline readonly">Read only </span>   
An [`HTMLElement`](htmlelement) object which identifies the button or other element which was invoked to trigger the form being submitted.

Methods
-------

*While `SubmitEvent` offers no methods of its own, it inherits any specified by its parent interface, [`Event`](event).*

Examples
--------

In this example, a shopping cart may have an assortment of different submit buttons depending on factors such as the user's settings, the shop's settings, and any minimum or maximum shopping card totals established by the payment processors. Each of the submit elements' [`id`](element/id) is used to identify which payment processor the button corresponds to.

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

The handler ID is obtained by using the `submit` event's [`submitter`](submitevent/submitter) property to get the submit button, from which we then get the ID. With that in hand, we can call a `processOrder()` function to handle the order, passing along the form and the handler ID.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/form-control-infrastructure.html#submitevent">HTML Living Standard<br />
<span class="small">The definition of 'SubmitEvent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SubmitEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SubmitEvent</a>
