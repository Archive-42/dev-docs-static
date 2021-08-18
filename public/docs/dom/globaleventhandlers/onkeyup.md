# GlobalEventHandlers.onkeyup

The `onkeyup` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `keyup` events.

The `keyup` event fires when the user releases a key that was previously pressed.

## Syntax

    target.onkeyup = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`KeyboardEvent`](../keyboardevent) object as its sole argument.

## Example

This example logs the [`KeyboardEvent.code`](../keyboardevent/code) value whenever you release a key inside the [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element.

### HTML

    <input>
    <p id="log"></p>

### JavaScript

    const input = document.querySelector('input');
    const log = document.getElementById('log');

    input.onkeyup = logKey;

    function logKey(e) {
      log.textContent += `${e.code}`;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-onkeyup">HTML Living Standard<br />
<span class="small">The definition of 'onkeyup' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onkeyup`

1

12

9

4

≤12.1

1

1

18

9

≤12.1

1

1.0

### Compatibility notes

Since Firefox 65, the `keyup` and `keydown` events are now fired during IME composition, to improve cross-browser compatibility for CJKT users ([bug 354358](https://bugzilla.mozilla.org/show_bug.cgi?id=354358), also see [keydown and keyup events are now fired during IME composition](https://github.com/mdn/kuma/issues/7647) for more useful details). To ignore all `keyup` events that are part of composition, do something like this (229 is a special value set for a `keyCode` relating to an even that has been processed by an IME):

    eventTarget.addEventListener("keyup", event => {
      if (event.isComposing || event.keyCode === 229) {
        return;
      }
      // do something
    });

## See also

- `keyup` event
- Related event handlers
  - [`GlobalEventHandlers.onkeydown`](onkeydown)
  - [`GlobalEventHandlers.onkeypress`](onkeypress)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeyup" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeyup</a>
