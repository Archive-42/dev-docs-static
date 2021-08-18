# Element: compositionupdate event

The `compositionupdate` event is fired when a new character is received in the context of a text composition session controlled by a text composition system such as an [input method editor](https://developer.mozilla.org/en-US/docs/Glossary/Input_method_editor).

For example, this event could be fired while a user enters a Chinese character using a [Pinyin](https://en.wikipedia.org/wiki/Pinyin) IME.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../compositionevent"><code>CompositionEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td>None</td></tr></tbody></table>

## Examples

    const inputElement = document.querySelector('input[type="text"]');

    inputElement.addEventListener('compositionupdate', (event) => {
      console.log(`generated characters were: ${event.data}`);
    });

### Live example

#### HTML

    <div class="control">
      <label for="name">On macOS, click in the textbox below,<br> then type <kbd>option</kbd> + <kbd>`</kbd>, then <kbd>a</kbd>:</label>
      <input type="text" id="example" name="example">
    </div>

    <div class="event-log">
      <label>Event log:</label>
      <textarea readonly class="event-log-contents" rows="8" cols="25"></textarea>
      <button class="clear-log">Clear</button>
    </div>

#### JS

    const inputElement = document.querySelector('input[type="text"]');
    const log = document.querySelector('.event-log-contents');
    const clearLog = document.querySelector('.clear-log');

    clearLog.addEventListener('click', () => {
        log.textContent = '';
    });

    function handleEvent(event) {
        log.textContent = log.textContent + `${event.type}: ${event.data}\n`;
    }

    inputElement.addEventListener('compositionstart', handleEvent);
    inputElement.addEventListener('compositionupdate', handleEvent);
    inputElement.addEventListener('compositionend', handleEvent);

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-compositionupdate">UI Events</a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`compositionupdate_event`

Yes

12

9

Yes

Yes

Yes

Yes

Yes

Yes

?

?

Yes

## See also

- Related events: [`compositionstart`](compositionstart_event), [`compositionend`](compositionend_event).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/compositionupdate_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/compositionupdate_event</a>
