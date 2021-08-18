GlobalEventHandlers.onmouseover
===============================

The `onmouseover` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `mouseover` events.

The `mouseover` event fires when the user moves the mouse over a particular element.

Syntax
------

    element.onmouseover = function;

Example
-------

This example adds an `onmouseover` and an `onmouseout` event to a paragraph. Try moving your mouse over and out of the element.

### HTML

    <p>Test your mouse on me!</p>

### JavaScript

    const p = document.querySelector('p');
    p.onmouseover = logMouseOver;
    p.onmouseout = logMouseOut;

    function logMouseOver() {
      p.textContent = 'MOUSE OVER detected';
    }

    function logMouseOut() {
      p.textContent = 'MOUSE OUT detected';
    }

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-onmouseover">HTML Living Standard<br />
<span class="small">The definition of 'onmouseover' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onmouseover`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseover" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseover</a>
