# Document: keyup event

The `keyup` event is fired when a key is released.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../keyboardevent"><code>KeyboardEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onkeyup"><code>onkeyup</code></a></td></tr></tbody></table>

The [`keydown`](keydown_event) and `keyup` events provide a code indicating which key is pressed, while [`keypress`](keypress_event) indicates which _character_ was entered. For example, a lowercase "a" will be reported as 65 by `keydown` and `keyup`, but as 97 by `keypress`. An uppercase "A" is reported as 65 by all events.

**Note:** If you're looking for a way to react to changes in an input's value, you should use the [`input` event](../htmlelement/input_event). Some changes are not detectable by `keyup`, for example pasting text from the context menu in a text input.

Since Firefox 65, the [`keydown`](keydown_event) and `keyup` events are now fired during IME composition, to improve cross-browser compatibility for CJKT users ([bug 354358](https://bugzilla.mozilla.org/show_bug.cgi?id=354358), also see [keydown and keyup events are now fired during IME composition](https://github.com/mdn/kuma/issues/7647) for more useful details). To ignore all `keyup` events that are part of composition, do something like this (229 is a special value set for a `keyCode` relating to an event that has been processed by an IME):

    eventTarget.addEventListener("keyup", event => {
      if (event.isComposing || event.keyCode === 229) {
        return;
      }
      // do something
    });

## Examples

This example logs the [`KeyboardEvent.code`](../keyboardevent/code) value whenever you release a key.

### addEventListener keyup example

    <p>Focus the IFrame first (e.g. by clicking in it), then try pressing some keys.</p>
    <p id="log"></p>

    const log = document.getElementById('log');

    document.addEventListener('keyup', logKey);

    function logKey(e) {
      log.textContent += `${e.code}`;
    }

### onkeyup equivalent

    document.onkeyup = logKey;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-keyup">UI Events</a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`keyup_event`

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

- [`keydown`](keydown_event)
- [`keypress`](keypress_event)
- [`Element`](../element): [`keyup`](../element/keyup_event) event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/keyup_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/keyup_event</a>
