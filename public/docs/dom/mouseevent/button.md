MouseEvent.button
=================

The `MouseEvent.button` read-only property indicates which button was pressed on the mouse to trigger the event.

This property only guarantees to indicate which buttons are pressed during events caused by pressing or releasing one or multiple buttons. As such, it is not reliable for events such as `mouseenter`, `mouseleave`, `mouseover`, `mouseout` or `mousemove`.

Users may change the configuration of buttons on their pointing device so that if an event's button property is zero, it may not have been caused by the button that is physically left–most on the pointing device; however, it should behave as if the left button was clicked in the standard button layout.

**Note:** Do not confuse this property with the [`MouseEvent.buttons`](buttons) property, which indicates which buttons are pressed for all mouse events types.

Syntax
------

    var buttonPressed = instanceOfMouseEvent.button

### Return value

A number representing a given button:

-   `0`: Main button pressed, usually the left button or the un-initialized state
-   `1`: Auxiliary button pressed, usually the wheel button or the middle button (if present)
-   `2`: Secondary button pressed, usually the right button
-   `3`: Fourth button, typically the *Browser Back* button
-   `4`: Fifth button, typically the *Browser Forward* button

As noted above, buttons may be configured differently to the standard "left to right" layout. A mouse configured for left-handed use may have the button actions reversed. Some pointing devices only have one button and use keyboard or other input mechanisms to indicate main, secondary, auxilary, etc. Others may have many buttons mapped to different functions and button values.

Example
-------

### HTML

    <button id="button" oncontextmenu="event.preventDefault();">Click here with your mouse...</button>
    <p id="log"></p>

### JavaScript

    let button = document.querySelector('#button');
    let log = document.querySelector('#log');
    button.addEventListener('mouseup', logMouseButton);

    function logMouseButton(e) {
      if (typeof e === 'object') {
        switch (e.button) {
          case 0:
            log.textContent = 'Left button clicked.';
            break;
          case 1:
            log.textContent = 'Middle button clicked.';
            break;
          case 2:
            log.textContent = 'Right button clicked.';
            break;
          default:
            log.textContent = `Unknown button code: ${e.button}`;
        }
      }
    }

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-MouseEvent-button">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'MouseEvent.button' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Compared to <a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html">Document Object Model (DOM) Level 2 Events Specification</a>, the return value can be negative.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-MouseEvent">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'MouseEvent.button' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`button`

1

12

1

9

10.6

3.1

1

18

4

11

2

1.0

See also
--------

-   [`MouseEvent`](../mouseevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/button" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/button</a>
