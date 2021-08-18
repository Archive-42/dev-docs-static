# FormDataEvent.formData

The `formData` read only property of the [`FormDataEvent`](../formdataevent) interface contains the [`FormData`](../formdata) object representing the data contained in the form when the event was fired.

## Syntax

    formData = formDataEvent.formData

### Returns

A [`FormData`](../formdata) object.

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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-formdataevent-formdata">HTML Living Standard<br />
<span class="small">The definition of 'formData' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

## See also

- [`XMLHTTPRequest`](../xmlhttprequest)
- [Using XMLHttpRequest](../xmlhttprequest/using_xmlhttprequest)
- [Using FormData objects](../formdata/using_formdata_objects)
- [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FormDataEvent/formData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FormDataEvent/formData</a>
