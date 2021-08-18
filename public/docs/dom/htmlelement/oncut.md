HTMLElement.oncut
=================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `HTMLElement.oncut` property of the [`HTMLElement`](../htmlelement) interface is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `cut` events.

The `cut` event fires when the user attempts to cut text.

Syntax
------

    target.oncut = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`ClipboardEvent`](../clipboardevent) object as its sole argument.

Example
-------

This example allows text to be copied from the [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea), but doesn't allow text to be cut. It also logs each copy and cut attempt.

### HTML

    <h3>Play with this text area:</h3>
    <textarea id="editor" rows="3">Try copying and cutting the text in this field!</textarea>

    <h3>Log:</h3>
    <p id="log"></p>

### JavaScript

    function logCopy(event) {
      log.innerText = 'Copied!\n' + log.innerText;
    }

    function preventCut(event) {
      event.preventDefault();
      log.innerText = 'Cut blocked!\n' + log.innerText;
    }

    const editor = document.getElementById('editor');
    const log = document.getElementById('log');

    editor.oncopy = logCopy;
    editor.oncut = preventCut;

### Result

Specifications
--------------

[WHATWG Standard](https://html.spec.whatwg.org/multipage/webappapis.html#handler-oncut)

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

`oncut`

1

12

9

5.5

≤12.1

3

1

18

9

≤12.1

1

1.0

Since Firefox 13, the preference `dom.event.clipboardevents.enabled` controls this feature. It defaults to `true` but can be disabled.

See also
--------

-   Clipboard API event `cut`
-   Related event handlers
    -   [`HTMLElement.oncopy`](oncopy)
    -   [`HTMLElement.onpaste`](onpaste)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/oncut" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/oncut</a>
