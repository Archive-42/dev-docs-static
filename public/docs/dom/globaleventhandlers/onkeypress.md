# GlobalEventHandlers.onkeypress

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `onkeypress` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `keypress` events.

The `keypress` event _should_ fire when the user presses a key on the keyboard. However, in practice browsers do not fire `keypress` events for certain keys.

The `onkeypress` event handler has been deprecated. You may want to use [`onkeydown`](onkeydown) instead.

## Syntax

    target.onkeypress = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`KeyboardEvent`](../keyboardevent) object as its sole argument.

## Examples

### Basic example

This example logs the [`KeyboardEvent.code`](../keyboardevent/code) value whenever you press a key inside the [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element.

#### HTML

    <input>
    <p id="log"></p>

#### JavaScript

    const input = document.querySelector('input');
    const log = document.getElementById('log');

    input.onkeypress = logKey;

    function logKey(e) {
      log.textContent += `${e.code}`;
    }

#### Result

### Filter keys with a regular expression

This example filters the characters typed into a form field using a [regular expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions).

#### HTML

    <label>Enter numbers only:
      <input>
    </label>

#### JavaScript

    function numbersOnly(event) {
      return event.charCode === 0 || /\d/.test(String.fromCharCode(event.charCode));
    }

    const input = document.querySelector('input');
    input.onkeypress = numbersOnly;

    // Prevent pasting (since pasted content might include non-number characters)
    input.onpaste = event => false;

#### Result

### Capture the typing of a hidden word

The following JavaScript function will do something after the user types the word "exit" in any point of a page.

    /* Type the word "exit" in any point of your page... */

    (function () {
      const sSecret = /* Choose your hidden word...: */ "exit";
      let nOffset = 0;

      document.onkeypress = function(oPEvt) {
        let oEvent = oPEvt || window.event,
            nChr = oEvent.charCode,
            sNodeType = oEvent.target.nodeName.toUpperCase();

        if (nChr === 0 ||
            oEvent.target.contentEditable.toUpperCase() === "TRUE" ||
            sNodeType === "TEXTAREA" ||
            sNodeType === "INPUT" && oEvent.target.type.toUpperCase() === "TEXT") {
          return true;
        }

        if (nChr !== sSecret.charCodeAt(nOffset)) {
          nOffset = nChr === sSecret.charCodeAt(0) ? 1 : 0;
        } else if (nOffset < sSecret.length - 1) {
          nOffset++;
        } else {
          nOffset = 0;
          /* Do something here... */
          alert("Yes!!!");
          location.assign("https://developer.mozilla.org/");
        }

        return true;
      };
    })();

**Note:** A more complete framework for capturing the typing of hidden words is [available on GitHub](https://github.com/madmurphy/spell.js/).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-onkeypress">HTML Living Standard<br />
<span class="small">The definition of 'onkeypress' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onkeypress`

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

- The `keypress` event is no longer fired for [non-printable keys](<../keyboardevent/keycode#non-printable_keys_(function_keys)>) (see [bug 968056](https://bugzilla.mozilla.org/show_bug.cgi?id=968056) for Firefox 65's implementation of this), except for the Enter key, and the Shift + Enter and Ctrl + Enter key combinations (these were kept for cross-browser compatibility purposes).

## See also

- `keypress` event
- Related event handlers
  - [`GlobalEventHandlers.onkeydown`](onkeydown)
  - [`GlobalEventHandlers.onkeyup`](onkeyup)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeypress" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onkeypress</a>
