# KeyboardEvent.key

The [`KeyboardEvent`](../keyboardevent) interface's `key` read-only property returns the value of the key pressed by the user, taking into consideration the state of modifier keys such as Shift as well as the keyboard locale and layout. The Unicode value of the key pressed can be derived from it using [`charCodeAt()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charCodeAt). Its value is determined as follows:

#### Key values

See a full list of [key values](key/key_values).

- If the pressed key has a printed representation, the returned value is a non-empty Unicode character string containing the printable representation of the key.
- If the pressed key is a control or special character, the returned value is one of the [pre-defined key values](key/key_values).
- If the `KeyboardEvent` represents the press of a [dead key](https://wikipedia.org/wiki/Dead_key), the key value must be "`Dead`".
- Some specialty keyboard keys (such as the extended keys for controlling media on multimedia keyboards) don't generate key codes on Windows; instead, they trigger `WM_APPCOMMAND` events. These events get mapped to DOM keyboard events, and are listed among the "Virtual key codes" for Windows, even though they aren't actually key codes.
- If the key cannot be identified, the returned value is `Unidentified`.

## KeyboardEvent sequence

Every `KeyboardEvent` is fired in a pre-determined sequence. For a given key press, the sequence of `KeyboardEvent`s fired is as follows assuming that [`Event.preventDefault`](../event/preventdefault) is not called:

1.  A [`keydown`](../element/keydown_event) event is first fired. If the key is held down further and the key produces a character key, then the event continues to be emitted in a platform implementation dependent interval and the [`KeyboardEvent.repeat`](repeat) read only property is set to `true`.
2.  If the key produces a character key that would result in a character being inserted into possibly an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) or an element with [`HTMLElement.contentEditable`](../htmlelement/contenteditable) set to true, the [`beforeinput`](../htmlelement/beforeinput_event) and [`input`](../htmlelement/input_event) event types are fired in that order. Note that some other implementations may fire [`keypress`](../element/keypress_event) event if supported. The events will be fired repeatedly while the key is held down.
3.  A [`keyup`](../element/keyup_event) event is fired once the key is released. This completes the process.

In sequence 1 & 3, the `KeyboardEvent.key` attribute is defined and is set appropriately to a value according to the rules defined earlier.

## KeyboardEvent sequence example

Consider the event sequence generated when we interact with the Shift and the 2 key using a U.S keyboard layout as compared to when we do so using a UK keyboard layout.

Try experimenting using the following two test cases:

1.  Press and hold the Shift key, then press 2 and release it. Next, release the Shift key.
2.  Press and hold the Shift key, then press and hold 2. Release the Shift key. Finally, release 2.

### HTML

    <div class="fx">
      <div>
        <textarea rows="5" name="test-target" id="test-target"></textarea>
        <button type="button" name="btn-clear-console" id="btn-clear-console">clear console</button>
      </div>
      <div class="flex">
        <pre id="console-log"></pre>
      </div>
    </div>

### CSS

    .fx {
      -webkit-display: flex;
      display: flex;
      margin-left: -20px;
      margin-right: -20px;
    }

    .fx > div {
      padding-left: 20px;
      padding-right: 20px;
    }

    .fx > div:first-child {
       width: 30%;
    }

    .flex {
      -webkit-flex: 1;
      flex: 1;
    }

    #test-target {
      display: block;
      width: 100%;
      margin-bottom: 10px;
    }

### JavaScript

    let textarea = document.getElementById('test-target'),
    consoleLog = document.getElementById('console-log'),
    btnClearConsole = document.getElementById('btn-clear-console');

    function logMessage(message) {
      document.getElementById("console-log").innerHTML += message + "<br>";
    }

    textarea.addEventListener('keydown', (e) => {
      if (!e.repeat)
        logMessage(`Key "${e.key}" pressed  [event: keydown]`);
      else
        logMessage(`Key "${e.key}" repeating  [event: keydown]`);
    });

    textarea.addEventListener('beforeinput', (e) => {
      logMessage(`Key "${e.data}" about to be input  [event: beforeinput]`);
    });

    textarea.addEventListener('input', (e) => {
      logMessage(`Key "${e.data}" input  [event: input]`);
    });

    textarea.addEventListener('keyup', (e) => {
      logMessage(`Key "${e.key}" released  [event: keyup]`);
    });

    btnClearConsole.addEventListener('click', (e) => {
      let child = consoleLog.firstChild;
      while (child) {
       consoleLog.removeChild(child);
       child = consoleLog.firstChild;
      }
    });

### Result

**Note:** On browsers that don't fully implement the [`InputEvent`](../inputevent) interface which is used for the [`beforeinput`](../htmlelement/beforeinput_event) and [`input`](../htmlelement/input_event) events, you may get incorrect output on those lines of the log output.

### Case 1

When the shift key is pressed, a [`keydown`](../element/keydown_event) event is first fired, and the `key` property value is set to the string `Shift`. As we keep holding this key, the [`keydown`](../element/keydown_event) event does not continue to fire repeatedly because it does not produce a character key.

When `key 2` is pressed, another [`keydown`](../element/keydown_event) event is fired for this new key press, and the `key` property value for the event is set to the string `@` for the U.S keyboard type and `"` for the UK keyboard type, because of the active modifier `shift` key. The [`beforeinput`](../htmlelement/beforeinput_event) and [`input`](../htmlelement/input_event) events are fired next because a character key has been produced.

As we release the `key 2`, a [`keyup`](../element/keyup_event) event is fired and the `key` property will maintain the string values `@` and `"` for the different keyboard layouts respectively.

As we finally release the `shift` key, another [`keyup`](../element/keyup_event) event is fired for it, and the key attribute value remains `Shift`.

### Case 2

When the shift key is pressed, a [`keydown`](../element/keydown_event) event is first fired, and the `key` property value is set to be the string `Shift`. As we keep holding this key, the keydown event does not continue to fire repeatedly because it produced no character key.

When `key 2` is pressed, another [`keydown`](../element/keydown_event) event is fired for this new key press, and the `key` property value for the event is set to be the string `@` for the U.S keyboard type and `"` for the UK keyboard type, because of the active modifier `shift` key. The [`beforeinput`](../htmlelement/beforeinput_event) and [`input`](../htmlelement/input_event)[`beforeinput`](../htmlelement/beforeinput_event) and [`input`](../htmlelement/input_event) events are fired next because a character key has been produced. As we keep holding the key, the [`keydown`](../element/keydown_event) event continues to fire repeatedly and the [`KeyboardEvent.repeat`](repeat) property is set to `true`. The [`beforeinput`](../htmlelement/beforeinput_event) and [`input`](../htmlelement/input_event) events are fired repeatedly as well.

As we release the `shift` key, a [`keyup`](../element/keyup_event) event is fired for it, and the key attribute value remains `Shift`. At this point, notice that the `key` property value for the repeating keydown event of the `key 2` key press is now "2" because the modifier `shift` key is no longer active. The same goes for the [`InputEvent.data`](../inputevent/data) property of the [`beforeinput`](../htmlelement/beforeinput_event) and [`input`](../htmlelement/input_event) events.

As we finally release the `key 2`, a [`keyup`](../element/keyup_event) event is fired but the `key` property will be set to the string value `2` for both keyboard layouts because the modifier `shift` key is no longer active.

## Example

This example uses [`EventTarget.addEventListener()`](../eventtarget/addeventlistener) to listen for [`keydown`](../element/keydown_event) events. When they occur, the key's value is checked to see if it's one of the keys the code is interested in, and if it is, it gets processed in some way (possibly by steering a spacecraft, perhaps by changing the selected cell in a spreadsheet).

    window.addEventListener("keydown", function (event) {
      if (event.defaultPrevented) {
        return; // Do nothing if the event was already processed
      }

      switch (event.key) {
        case "Down": // IE/Edge specific value
        case "ArrowDown":
          // Do something for "down arrow" key press.
          break;
        case "Up": // IE/Edge specific value
        case "ArrowUp":
          // Do something for "up arrow" key press.
          break;
        case "Left": // IE/Edge specific value
        case "ArrowLeft":
          // Do something for "left arrow" key press.
          break;
        case "Right": // IE/Edge specific value
        case "ArrowRight":
          // Do something for "right arrow" key press.
          break;
        case "Enter":
          // Do something for "enter" or "return" key press.
          break;
        case "Esc": // IE/Edge specific value
        case "Escape":
          // Do something for "esc" key press.
          break;
        default:
          return; // Quit when this doesn't handle the key event.
      }

      // Cancel the default action to avoid it being handled twice
      event.preventDefault();
    }, true);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#dom-keyboardevent-key">UI Events<br />
<span class="small">The definition of 'KeyboardEvent.key' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-KeyboardEvent-key">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'KeyboardEvent.key' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition, included key values.</td></tr></tbody></table>

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

`key`

51

12

23

9

IE's implementation does not completely match the current spec because it is based on an older version of the spec.

38

10

51

51

23

41

10

5.0

`dead_key`

51

≤79

No

No

38

?

51

51

No

41

?

5.0

`non_printable_keys`

51

12

23

9

IE's implementation does not completely match the current spec because it is based on an older version of the spec.

38

?

51

51

23

41

?

5.0

`printable_key`

51

12

29

9

IE's implementation does not completely match the current spec because it is based on an older version of the spec.

38

?

51

51

29

41

?

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/key" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/key</a>
