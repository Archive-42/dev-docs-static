# HTMLInputElement: invalid event

The `invalid` event fires when a submittable element has been checked for validity and doesn't satisfy its constraints.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/oninvalid"><code>GlobalEventHandlers.oninvalid</code></a></td></tr></tbody></table>

This event can be useful for displaying a summary of the problems with a form on submission. When a form is submitted, `invalid` events are fired at each form control that is invalid. The validity of submittable elements is checked before submitting their owner [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form), or after the [`checkValidity()`](https://developer.mozilla.org/en-US/docs/Learn/Forms#constraint_validation_api) method of the element or its owner `<form>` is called.

It is not checked on [`blur`](../element/blur_event).

## Examples

If a form is submitted with an invalid value, the submittable elements are checked and, if an error is found, the `invalid` event will fire on the `invalid` element. In this example, when an invalid event fires because of an invalid value in the input, the invalid value is logged.

### HTML

    <form action="#">
      <ul>
        <li><label>Enter an integer between 1 and 10: <input type="number" min="1" max="10" required></label></li>
        <li><input type="submit" value="submit"></li>
      </ul>
    </form><p id="log"></p>

### JavaScript

    const input = document.querySelector('input')
    const log = document.getElementById('log')

    input.addEventListener('invalid', logValue)

    function logValue(e) {
      log.textContent += e.target.value
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#the-constraint-validation-api">HTML Living Standard<br />
<span class="small">The definition of 'Invalid event' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/sec-forms.html#the-constraint-validation-api">HTML 5.1<br />
<span class="small">The definition of 'Invalid event' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/forms.html#the-constraint-validation-api">HTML5<br />
<span class="small">The definition of 'Invalid event' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`invalid_event`

10

12

4

10

10

5

4

18

64

12

5

4.0

## See also

- HTML [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) element
- Related event: [`submit`](../htmlformelement/submit_event)
- CSS [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) pseudo class

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/invalid_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/invalid_event</a>
