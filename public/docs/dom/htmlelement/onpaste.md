HTMLElement.onpaste
===================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `HTMLElement.onpaste` property of the [`HTMLElement`](../htmlelement) interface is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `paste` events.

The `paste` event fires when the user attempts to paste text.

Note that there is currently no DOM-only way to obtain the text being pasted; you'll have to use an <span class="page-not-created">`nsIClipboard`</span> to get that information.

Syntax
------

    target.onpaste = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`ClipboardEvent`](../clipboardevent) object as its sole argument.

Example
-------

This example logs every copy and paste attempt to the [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea).

### HTML

    <h3>Play with this text area:</h3>
    <textarea id="editor" rows="3">Try copying and pasting text into this field!</textarea>

    <h3>Log:</h3>
    <p id="log"></p>

### JavaScript

    function logCopy(event) {
      log.innerText = 'Copied!\n' + log.innerText;
    }

    function logPaste(event) {
      log.innerText = 'Pasted!\n' + log.innerText;
    }

    const editor = document.getElementById('editor');
    const log = document.getElementById('log');

    editor.oncopy = logCopy;
    editor.onpaste = logPaste;

### Result

Specifications
--------------

[WHATWG Standard](https://html.spec.whatwg.org/multipage/webappapis.html#handler-onpaste)

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

`onpaste`

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

-   Clipboard API event `paste`
-   Related event handlers
    -   [`HTMLElement.oncopy`](oncopy)
    -   [`HTMLElement.oncut`](oncut)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/onpaste" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/onpaste</a>
