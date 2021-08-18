# HTMLFormElement: reset event

The `reset` event fires when a [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) is reset.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes (although specified as a simple event that doesn't bubble)</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onreset"><code>GlobalEventHandlers.onreset</code></a></td></tr></tbody></table>

## Examples

This example uses [`EventTarget.addEventListener()`](../eventtarget/addeventlistener) to listen for form resets, and logs the current [`Event.timeStamp`](../event/timestamp) whenever that occurs.

### HTML

    <form id="form">
      <label>Test field: <input type="text"></label>
      <br><br>
      <button type="reset">Reset form</button>
    </form>
    <p id="log"></p>

### JavaScript

    function logReset(event) {
      log.textContent = `Form reset! Time stamp: ${event.timeStamp}`;
    }

    const form = document.getElementById('form');
    const log = document.getElementById('log');
    form.addEventListener('reset', logReset);

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-reset">HTML Living Standard<br />
<span class="small">The definition of 'reset' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/fullindex.html#eventdef-global-reset">HTML 5.2<br />
<span class="small">The definition of 'reset' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html51/fullindex.html#eventdef-global-reset">HTML 5.1<br />
<span class="small">The definition of 'reset' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Added info that the event is not trusted.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/index.html#events-0">HTML5<br />
<span class="small">The definition of 'reset' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`reset_event`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

## See also

- HTML [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) element

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/reset_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/reset_event</a>
