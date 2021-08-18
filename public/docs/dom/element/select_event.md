Element: select event
=====================

The `select` event fires when some text has been selected.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../uievent"><code>UIEvent</code></a> if generated from a user interface, <a href="../event"><code>Event</code></a> otherwise</td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onselect"><code>onselect</code></a></td></tr></tbody></table>

The event is not available for all elements in all languages. For example, in HTML, `select` events can be dispatched only on form `<input type="text">` and [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) elements.

Examples
--------

### Selection logger

    <input value="Try selecting some text in this element.">
    <p id="log"></p>

    function logSelection(event) {
      const log = document.getElementById('log');
      const selection = event.target.value.substring(event.target.selectionStart, event.target.selectionEnd);
      log.textContent = `You selected: ${selection}`;
    }

    const input = document.querySelector('input');
    input.addEventListener('select', logSelection);

### onselect equivalent

You can also set up the event handler using the [`onselect`](../globaleventhandlers/onselect) property:

    input.onselect = logSelection;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-select">UI Events<br />
<span class="small">The definition of 'select' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`select_event`

Yes

≤18

Yes

?

?

?

Yes

Yes

Yes

?

?

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/select_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/select_event</a>
