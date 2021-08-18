# GlobalEventHandlers.onformdata

The `onformdata` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for processing `formdata` events, fired after the entry list representing the form's data is constructed. This happens when the form is submitted, but can also be triggered by the invocation of a [`FormData()`](../formdata/formdata) constructor. `onformdata` is available on [`HTMLFormElement`](../htmlformelement).

## Syntax

    target.onformdata = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`FormDataEvent`](../formdataevent) object as its sole argument.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-onformdata">HTML Living Standard<br />
<span class="small">The definition of 'onformdata' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onformdata`

77

79

72

No

64

No

77

77

79

55

No

12.0

## See also

- [`formdata` event](../htmlformelement/formdata_event)
- [`FormDataEvent`](../formdataevent)
- [Using FormData Objects](../formdata/using_formdata_objects)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onformdata" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onformdata</a>
