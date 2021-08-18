HTMLFormElement: submit event
=============================

The `submit` event fires when a [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) is submitted.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes (although specified as a simple event that doesn't bubble)</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../submitevent"><code>SubmitEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onsubmit"><code>GlobalEventHandlers.onsubmit</code></a></td></tr></tbody></table>

Note that the `submit` event fires on the `<form>` element itself, and not on any [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) or [&lt;input type="submit"&gt;](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/submit) inside it. However, the [`SubmitEvent`](../submitevent) which is sent to indicate the form's submit action has been triggered includes a [`submitter`](../submitevent/submitter) property, which is the button that was invoked to trigger the submit request.

The `submit` event fires when the user clicks a submit button ([`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) or [&lt;input type="submit"&gt;](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/submit)) or presses Enter while editing a field (e.g. [&lt;input type="text"&gt;](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/text)) in a form. The event is not sent to the form when calling the [`form.submit()`](submit) method directly.

**Note:** Trying to submit a form that does not pass [validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation) triggers an [`invalid`](../htmlinputelement/invalid_event) event. In this case, the validation prevents form submission, and thus there is no `submit` event.

Examples
--------

This example uses [`EventTarget.addEventListener()`](../eventtarget/addeventlistener) to listen for form submit, and logs the current [`Event.timeStamp`](../event/timestamp) whenever that occurs, then prevents the default action of submitting the form.

### HTML

    <form id="form">
      <label>Test field: <input type="text"></label>
      <br><br>
      <button type="submit">Submit form</button>
    </form>
    <p id="log"></p>

### JavaScript

    function logSubmit(event) {
      log.textContent = `Form Submitted! Time stamp: ${event.timeStamp}`;
      event.preventDefault();
    }

    const form = document.getElementById('form');
    const log = document.getElementById('log');
    form.addEventListener('submit', logSubmit);

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-submit">HTML Living Standard<br />
<span class="small">The definition of 'submit' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/fullindex.html#eventdef-global-submit">HTML 5.2<br />
<span class="small">The definition of 'submit' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html51/fullindex.html#eventdef-global-submit">HTML 5.1<br />
<span class="small">The definition of 'submit' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/index.html#events-0">HTML5<br />
<span class="small">The definition of 'submit' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`submit_event`

1

12

1

9

8

3

1

18

4

10.1

1

1.0

See also
--------

-   HTML [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) element
-   Related event: [`invalid`](../htmlinputelement/invalid_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/submit_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/submit_event</a>
