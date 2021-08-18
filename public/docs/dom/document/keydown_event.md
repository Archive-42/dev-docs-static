# Document: keydown event

The `keydown` event is fired when a key is pressed.

Unlike the [`keypress`](keypress_event) event, the `keydown` event is fired for all keys, regardless of whether they produce a character value.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../keyboardevent"><code>KeyboardEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onkeydown"><code>onkeydown</code></a></td></tr></tbody></table>

The `keydown` and [`keyup`](keyup_event) events provide a code indicating which key is pressed, while [`keypress`](keypress_event) indicates which _character_ was entered. For example, a lowercase "a" will be reported as 65 by `keydown` and `keyup`, but as 97 by `keypress`. An uppercase "A" is reported as 65 by all events.

Since Firefox 65, the `keydown` and [`keyup`](keyup_event) events are now fired during IME composition ([bug 354358](https://bugzilla.mozilla.org/show_bug.cgi?id=354358)). To ignore all `keydown` events that are part of composition, do something like this (229 is a special value set for a `keyCode` relating to an event that has been processed by an IME):

    eventTarget.addEventListener("keydown", event => {
      if (event.isComposing || event.keyCode === 229) {
        return;
      }
      // do something
    });

## Examples

### addEventListener keydown example

This example logs the [`KeyboardEvent.code`](../keyboardevent/code) value whenever you press down a key.

    <p>Focus the IFrame first (e.g. by clicking in it), then try pressing some keys.</p>
    <p id="log"></p>

    document.addEventListener('keydown', logKey);

    function logKey(e) {
      log.textContent += `${e.code}`;
    }

### onkeydown equivalent

    document.onkeydown = logKey;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-keydown">UI Events</a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`keydown_event`

1

12

14

9

11.6

2

1

18

14

12

1

1.0

## See also

- [`keypress`](keypress_event)
- [`keyup`](keyup_event)
- [`Element`](../element): [`keydown`](../element/keydown_event) event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/keydown_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/keydown_event</a>
