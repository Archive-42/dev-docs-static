GlobalEventHandlers.onmouseout
==============================

The `onmouseout` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `mouseout` events.

The `mouseout` event fires when the mouse leaves an element. For example, when the mouse moves off of an image in the web page, the `mouseout` event is raised for that image element.

Syntax
------

    element.onmouseout = function;

Example
-------

This example adds an `onmouseout` and an `onmouseover` event to a paragraph. Try moving your mouse over and out of the element.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-onmouseout">HTML Living Standard<br />
<span class="small">The definition of 'onmouseout' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onmouseout`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseout" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseout</a>
