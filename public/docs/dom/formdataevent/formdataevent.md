FormDataEvent()
===============

The `FormDataEvent()` constructor creates a new [`FormDataEvent`](../formdataevent) object instance.

Syntax
------

    new FormDataEvent(type[, formEventInit]);

### Values

`type`  
A [`DOMString`](../domstring) representing the name of the event.

 `formEventInit` <span class="badge inline optional">Optional</span>   
A `FormEventInit` dictionary, which can take the following optional fields:

-   `bubbles`: a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the event bubbles. The default is `false`.
-   `cancelable`: a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the event can be cancelled. The default is `false`.
-   `composed`: a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the event will trigger listeners outside of a shadow root (see [`Event.composed`](../event/composed) for more details). The default is `false`.
-   `formData`: A [`FormData`](../formdata) object to pre-populate the FormDataEvent with. This would then be accessed through the [`FormDataEvent.formData`](formdata) property.

Examples
--------

    let fd = new FormData();
    fd.append('test', 'test');

    let fdEv = new FormDataEvent('formdata', { formData: fd });

    for (let value of fdEv.formData.values()) {
      console.log(value);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/form-control-infrastructure.html#the-formdataevent-interface">HTML Living Standard<br />
<span class="small">The definition of 'FormDataEvent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

See also
--------

-   [`FormDataEvent`](../formdataevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FormDataEvent/FormDataEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FormDataEvent/FormDataEvent</a>
