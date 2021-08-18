# HTMLElement.oncopy

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `oncopy` property of the [`HTMLElement`](../htmlelement) interface is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes [`copy`](../element/copy_event) events.

The `copy` event fires when the user attempts to copy text.

## Syntax

    target.oncopy = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`ClipboardEvent`](../clipboardevent) object as its sole argument.

## Example

This example blocks every copy and paste attempt from the [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea).

### HTML

    <h3>Play with this text area:</h3>
    <textarea id="editor" rows="3">Try copying and pasting text into this field!</textarea>

    <h3>Log:</h3>
    <p id="log"></p>

### JavaScript

    const log = document.getElementById('log');

    function logCopy(event) {
      log.innerText = 'Copy blocked!\n' + log.innerText;
      event.preventDefault();
    }

    function logPaste(event) {
      log.innerText = 'Paste blocked!\n' + log.innerText;
      event.preventDefault();
    }

    const editor = document.getElementById('editor');

    editor.oncopy = logCopy;
    editor.onpaste = logPaste;

### Result

## Specifications

[WHATWG Standard](https://html.spec.whatwg.org/multipage/webappapis.html#handler-oncopy)

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

`oncopy`

1

12

3

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

Since Firefox 13, the preference `dom.event.clipboardevents.enabled` controls this feature. It defaults to `true` but can be disabled.

## See also

- Clipboard API event [`copy`](../element/copy_event)
- Related event handlers
  - [`HTMLElement.oncut`](oncut)
  - [`HTMLElement.onpaste`](onpaste)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/oncopy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/oncopy</a>
