GlobalEventHandlers.oninvalid
=============================

The `oninvalid` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `invalid` events.

The `invalid` event fires when a submittable element has been checked and doesn't satisfy its constraints. The validity of submittable elements is checked before submitting their owner form, or after the `checkValidity()` method of the element or its owner form is called.

Syntax
------

    target.oninvalid = functionRef;
    var functionRef = target.oninvalid;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`Event`](../event) object as its sole argument.

Example
-------

This example demonstrates `oninvalid` and [`onsubmit`](onsubmit) event handlers on a form.

### HTML

    <form id="form">
      <p id="error" hidden>Please fill out all fields.</p>

      <label for="city">City</label>
      <input type="text" id="city" required>

      <button type="submit">Submit</button>
    </form>
    <p id="thanks" hidden>Your data has been received. Thanks!</p>

### JavaScript

    const form = document.getElementById('form');
    const error = document.getElementById('error');
    const city = document.getElementById('city');
    const thanks = document.getElementById('thanks');

    city.oninvalid = invalid;
    form.onsubmit = submit;

    function invalid(event) {
      error.removeAttribute('hidden');
    }

    function submit(event) {
      form.setAttribute('hidden', '');
      thanks.removeAttribute('hidden');

      // For this example, don't actually submit the form
      event.preventDefault();
    }

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-oninvalid">HTML Living Standard<br />
<span class="small">The definition of 'oninvalid' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`oninvalid`

4

13

9

No

≤12.1

5

≤37

18

9

≤12.1

4

1.0

See also
--------

-   `invalid` event
-   [DOM on-event handlers](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oninvalid" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/oninvalid</a>
