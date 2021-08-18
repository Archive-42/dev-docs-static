GlobalEventHandlers.onselect
============================

The `onselect` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes [`select` events](../element/select_event).

The `select` event only fires after text inside an `<input type="text">` or [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) is selected.

Syntax
------

    target.onselect = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`UIEvent`](../uievent) object as its sole argument.

Examples
--------

This example logs the text you select inside a [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) element.

### HTML

    <textarea>Try selecting some text in this element.</textarea>
    <p id="log"></p>

### JavaScript

    function logSelection(event) {
      const log = document.getElementById('log');
      const selection = event.target.value.substring(event.target.selectionStart, event.target.selectionEnd);
      log.textContent = `You selected: ${selection}`;
    }

    const textarea = document.querySelector('textarea');
    textarea.onselect = logSelection;

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-onselect">HTML Living Standard<br />
<span class="small">The definition of 'onselect' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onselect`

1

12

9

9

≤12.1

1

1

18

9

≤12.1

1

1.0

See also
--------

-   [`select` event](../element/select_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselect</a>
