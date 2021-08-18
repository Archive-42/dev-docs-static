FormDataEvent
=============

The `FormDataEvent` interface represents a [`formdata` event](htmlformelement/formdata_event) — such an event is fired on an [`HTMLFormElement`](htmlformelement) object after the entry list representing the form's data is constructed. This happens when the form is submitted, but can also be triggered by the invocation of a [`FormData()`](formdata/formdata) constructor.

This allows a [`FormData`](formdata) object to be quickly obtained in response to a `formdata` event firing, rather than needing to put it together yourself when you wish to submit form data via a method like [`XMLHttpRequest`](xmlhttprequest) (see [Using FormData objects](formdata/using_formdata_objects)).

Constructor
-----------

[`FormDataEvent()`](formdataevent/formdataevent)  
Creates a new `FormDataEvent` object instance.

Properties
----------

*Inherits properties from its parent interface, [`Event`](event).*

[`FormDataEvent.formData`](formdataevent/formdata)  
Contains the [`FormData`](formdata) object representing the data contained in the form when the event was fired.

Methods
-------

*Inherits methods from its parent interface, [`Event`](event).*

Examples
--------

    // grab reference to form

    const formElem = document.querySelector('form');

    // submit handler

    formElem.addEventListener('submit', (e) => {
      // on form submission, prevent default
      e.preventDefault();

      // construct a FormData object, which fires the formdata event
      new FormData(formElem);
    });

    // formdata handler to retrieve data

    formElem.addEventListener('formdata', (e) => {
      console.log('formdata fired');

      // Get the form data from the event object
      let data = e.formData;
      for (var value of data.values()) {
        console.log(value);
      }

      // submit the data via XHR
      var request = new XMLHttpRequest();
      request.open("POST", "/formHandler");
      request.send(data);
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/form-control-infrastructure.html#the-formdataevent-interface">HTML Living Standard<br />
<span class="small">The definition of 'FormDataEvent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`FormDataEvent`

77

79

72

No

64

No

77

77

No

55

No

12.0

`FormDataEvent`

77

79

72

No

64

No

77

77

No

55

No

12.0

`formData`

77

79

72

No

64

No

77

77

No

55

No

12.0

See also
--------

-   [`XMLHTTPRequest`](xmlhttprequest)
-   [`FormData`](formdata)
-   [Using FormData objects](formdata/using_formdata_objects)
-   [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FormDataEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FormDataEvent</a>
