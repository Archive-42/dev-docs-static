# HTMLFormElement: formdata event

The `formdata` event fires after the entry list representing the form's data is constructed. This happens when the form is submitted, but can also be triggered by the invocation of a [`FormData()`](../formdata/formdata) constructor.

## General info

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../formdataevent"><code>FormDataEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onformdata"><code>GlobalEventHandlers.onformdata</code></a></td></tr></tbody></table>

## Examples

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

The `onformdata` version would look like this:

    formElem.onformdata = (e) => {
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
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-formdata">HTML Living Standard<br />
<span class="small">The definition of 'formdata' in that specification.</span></a></td><td><span class="spec-">Unknown</span></td><td></td></tr></tbody></table>

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

`formdata_event`

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

## See also

- HTML [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) element
- [`FormDataEvent`](../formdataevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/formdata_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/formdata_event</a>
