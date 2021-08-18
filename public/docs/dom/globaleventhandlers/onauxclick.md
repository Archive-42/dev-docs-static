GlobalEventHandlers.onauxclick
==============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `onauxclick` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for processing `auxclick` events.

The `auxclick` event is raised when a non-primary button has been pressed on an input device (e.g., a middle mouse button). It fires after the `mousedown` and `mouseup` events, in that order.

**Note:** Browser vendors are implementing this property as part of a plan to improve compatibility with regards to button behaviors. Specifically, event behavior is being updated so that `click` only fires for primary button clicks (e.g., left mouse button), while `auxclick` fires for non-primary button clicks. Historically, `click` has generally fired for the click of *any* device input button, although with browser behavior being somewhat inconsistent.

Syntax
------

    target.onauxclick = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`MouseEvent`](../mouseevent) object as its sole argument. Within the function, `this` will be the element upon which the event was triggered.

Only one `onauxclick` handler can be assigned to an object at a time. You may prefer to use the [`EventTarget.addEventListener()`](../eventtarget/addeventlistener) method instead, since it's more flexible.

Example
-------

In this example we define functions for two event handlers — [`onclick`](onclick) and `onauxclick`. The former changes the color of the button background, while the latter changes the button foreground (text) color. You can see the two functions in action by trying the demo out with a multi-button mouse ([see it live on GitHub](https://mdn.github.io/dom-examples/auxclick/); also [see the source code](https://github.com/mdn/dom-examples/blob/master/auxclick/index.html)).

    var button = document.querySelector('button');
    var html = document.querySelector('html');

    function random(number) {
      return Math.floor(Math.random() * number);
    }

    button.onclick = function() {
      var rndCol = 'rgb(' + random(255) + ',' + random(255) + ',' + random(255) + ')';
      button.style.backgroundColor = rndCol;
    };

    button.onauxclick = function() {
      var rndCol = 'rgb(' + random(255) + ',' + random(255) + ',' + random(255) + ')';
      button.style.color = rndCol;
    }

**Note**: If you are using a three-button mouse, you'll notice that the `onauxclick` handler is run when either of the non-left mouse buttons are clicked.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-auxclick">UI Events<br />
<span class="small">The definition of 'onauxclick' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`onauxclick`

55

79

53

No

42

No

55

55

53

42

No

6.0

See also
--------

-   `auxclick` event
-   Related event handlers
    -   [`GlobalEventHandlers.onclick`](onclick)
    -   [`GlobalEventHandlers.ondblclick`](ondblclick)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onauxclick" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onauxclick</a>
