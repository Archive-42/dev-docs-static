MouseEvent.buttons
==================

The `MouseEvent.buttons` read-only property indicates which buttons are pressed on the mouse (or other input device) when a mouse event is triggered.

Each button that can be pressed is represented by a given number (see below). If more than one button is pressed, the button values are added together to produce a new number. For example, if the secondary (`2`) and auxilary (`4`) buttons are pressed simultaneously, the value is `6` (i.e., `2 + 4`).

**Note:** Do not confuse this property with the [`MouseEvent.button`](button) property. The [`MouseEvent.buttons`](buttons) property indicates the state of buttons pressed during any kind of mouse event, while the [`MouseEvent.button`](button) property only guarantees the correct value for mouse events caused by pressing or releasing one or multiple buttons.

Syntax
------

    var buttonsPressed = instanceOfMouseEvent.buttons

### Return value

A number representing one or more buttons. For more than one button pressed simultaneously, the values are combined (e.g., `3` is primary + secondary).

-   `0 ` : No button or un-initialized
-   `1 ` : Primary button (usually the left button)
-   `2 ` : Secondary button (usually the right button)
-   `4 ` : Auxiliary button (usually the mouse wheel button or middle button)
-   `8 ` : 4th button (typically the "Browser Back" button)
-   `16` : 5th button (typically the "Browser Forward" button)

Example
-------

This example logs the `buttons` property when you trigger a `mousedown` event.

### HTML

    <p>Click anywhere with one or more mouse buttons.</p>
    <pre id="log">buttons: </pre>

### JavaScript

    let log = document.createTextNode('?');   // let log = new Text('?');

    function logButtons(e) {
      log.data = `${e.buttons} (${e.type})`;  // log.nodeValue= `${e.buttons} (${e.type})`;
    }

    document.addEventListener('mouseup', logButtons);
    document.addEventListener('mousedown', logButtons);
    // document.addEventListener('mousemove', logButtons);

    document.querySelector('#log').appendChild(log)

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#dom-mouseevent-buttons">UI Events<br />
<span class="small">The definition of 'MouseEvent.buttons' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Current working draft</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-MouseEvent-buttons">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'MouseEvent.buttons' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`buttons`

43

12

Yes

Resrictions apply depending on OS.

9

Yes

11.1

No

No

Yes

Yes

11.3

No

### Firefox notes

Firefox supports the `buttons` attribute on Windows, Linux (GTK), and macOS with the following restrictions:

-   Utilities allow customization of button actions. Therefore, *primary* might not be the left button on the device, *secondary* might not be the right button, and so on. Moreover, the middle (wheel) button, 4th button, and 5th button might not be assigned a value, even when they are pressed.
-   Single-button devices may emulate additional buttons with combinations of button and keyboard presses.
-   Touch devices may emulate buttons with configurable gestures (e.g., one-finger touch for *primary*, two-finger touch for *secondary*, etc.).
-   On Linux (GTK), the 4th button and the 5th button are not supported. In addition, a `mouseup` event always includes the releasing button information in the `buttons` value.
-   On Mac OS X 10.5, the `buttons` attribute always returns `0` because there is no platform API for implementing this feature.

See also
--------

-   [`MouseEvent`](../mouseevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/buttons" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/buttons</a>
