GlobalEventHandlers.onclick
===========================

The `onclick` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for processing [`click`](../element/click_event) events on a given element.

The `click` event is raised when the user clicks on an element. It fires after the [`mousedown`](../element/mousedown_event) and [`mouseup`](../element/mouseup_event) events, in that order.

**Note:** When using the `click` event to trigger an action, also consider adding this same action to the [`keydown`](../element/keydown_event) event, to allow the use of that same action by people who don't use a mouse or a touch screen.

Syntax
------

    target.onclick = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`MouseEvent`](../mouseevent) object as its sole argument. Within the function, [`this`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this) will be the object that `onclick` was bound too (which will also match `event.currentTarget`)

Only one `onclick` handler can be assigned to an object at a time. You may prefer to use the [`EventTarget.addEventListener()`](../eventtarget/addeventlistener) method instead, since it's more flexible.

Examples
--------

### Detecting clicks

This example changes the color of an element when it's clicked upon.

#### HTML

    <div id="demo">Click here</div>

#### JavaScript

    document.getElementById('demo').onclick = function changeContent() {

       document.getElementById('demo').textContent = "Help me";
       document.getElementById('demo').style = "Color: red";

    }

#### Result

### Getting the coordinates of clicks

This example displays the coordinates at which the most recent mouse button click occurred.

#### HTML

    <p>Click anywhere in this example.</p>
    <p id="log"></p>

#### JavaScript

    let log = document.getElementById('log');

    document.onclick = inputChange;

    function inputChange(e) {
      log.textContent = `Position: (${e.clientX}, ${e.clientY})`;
    }

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-onclick">HTML Living Standard<br />
<span class="small">The definition of 'onclick' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onclick`

1

12

1

4

9

3

1

18

4

10.1

1

1.0

See also
--------

-   [`click`](../element/click_event) event
-   Related event handlers
    -   [`GlobalEventHandlers.onauxclick`](onauxclick)
    -   [`GlobalEventHandlers.ondblclick`](ondblclick)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onclick" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onclick</a>
