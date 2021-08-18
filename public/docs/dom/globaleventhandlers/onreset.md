GlobalEventHandlers.onreset
===========================

The `onreset` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `reset` events.

The `reset` event fires when the user clicks a reset button in a form (`<input type="reset">`).

Syntax
------

    target.onreset = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives an [`Event`](../event) object as its sole argument.

Example
-------

This example logs the current [`Event.timeStamp`](../event/timestamp) whenever you reset the form.

### HTML

    <form id="form">
      <label>Test field: <input type="text"></label>
      <br><br>
      <button type="reset">Reset form</button>
    </form>
    <p id="log"></p>

### JavaScript

    function logReset(event) {
      log.textContent = `Form reset! Time stamp: ${event.timeStamp}`;
    }

    const form = document.getElementById('form');
    const log = document.getElementById('log');
    form.onreset = logReset;

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-onreset">HTML Living Standard<br />
<span class="small">The definition of 'onreset' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onreset`

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

-   `reset` event
-   HTML [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) element

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onreset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onreset</a>
