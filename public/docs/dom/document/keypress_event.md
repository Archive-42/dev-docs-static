# Document: keypress event

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `keypress` event is fired when a key that produces a character value is pressed down. Examples of keys that produce a character value are alphabetic, numeric, and punctuation keys. Examples of keys that don't produce a character value are modifier keys such as Alt, Shift, Ctrl, or Meta.

Since this event has been deprecated, you should look to use `beforeinput` or `keydown` instead.

<table><tbody><tr class="odd"><td>Interface</td><td><a href="../keyboardevent"><code>KeyboardEvent</code></a></td></tr><tr class="even"><td>Bubbles</td><td>Yes</td></tr><tr class="odd"><td>Cancelable</td><td>Yes</td></tr><tr class="even"><td>Default Action</td><td>Varies: <code>keypress</code> event; launch text composition system; <code>blur</code> and <code>focus</code> events; <code>DOMActivate</code> event; other event</td></tr></tbody></table>

## Examples

### addEventListener keypress example

This example logs the [`KeyboardEvent.code`](../keyboardevent/code) value whenever you press a key.

    <p>Press inside this IFrame first to focus it, then try pressing keys on the keyboard.</p>
    <p id="log"></p>

    const log = document.getElementById('log');

    document.addEventListener('keypress', logKey);

    function logKey(e) {
      log.textContent += `${e.code}`;
    }

### onkeypress equivalent

    document.onkeypress = logKey;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-keypress">UI Events</a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`keypress_event`

1

Chrome does not fire the `keypress` event for [known keyboard shortcuts](https://crbug.com/13891#c50). Which keyboard shortcuts are known depends on the user's system. Use the `keydown` event to implement keyboard shortcuts.

12

14

As of Firefox 65, the `keypress` event is no longer fired for [non-printable keys](<https://developer.mozilla.org/docs/Web/API/KeyboardEvent/keyCode#Non-printable_keys_(function_keys)>), except for the Enter key, and the Shift + Enter and Ctrl + Enter key combinations (these were kept for cross-browser compatibility purposes).

9

11.6

2

1

Chrome does not fire the `keypress` event for [known keyboard shortcuts](https://crbug.com/13891#c50). Which keyboard shortcuts are known depends on the user's system. Use the `keydown` event to implement keyboard shortcuts.

18

Chrome does not fire the `keypress` event for [known keyboard shortcuts](https://crbug.com/13891#c50). Which keyboard shortcuts are known depends on the user's system. Use the `keydown` event to implement keyboard shortcuts.

14

As of Firefox 65, the `keypress` event is no longer fired for [non-printable keys](<https://developer.mozilla.org/docs/Web/API/KeyboardEvent/keyCode#Non-printable_keys_(function_keys)>), except for the Enter key, and the Shift + Enter and Ctrl + Enter key combinations (these were kept for cross-browser compatibility purposes).

12

1

1.0

Samsung Internet does not fire the `keypress` event for [known keyboard shortcuts](https://crbug.com/13891#c50). Which keyboard shortcuts are known depends on the user's system. Use the `keydown` event to implement keyboard shortcuts.

## See also

- [`GlobalEventHandlers.onkeypress`](../globaleventhandlers/onkeypress)
- The [`Element`](../element) interface, which the event also targets.
- Related events:
  - `keydown`
  - `keyup`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/keypress_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/keypress_event</a>
