MouseEvent.ctrlKey
==================

The `MouseEvent.ctrlKey` read-only property is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether the ctrl key was pressed or not when a given mouse event occurs.

**Note:** On Macintosh keyboards, this key is the control key.

Syntax
------

    var ctrlKeyPressed = instanceOfMouseEvent.ctrlKey

### Return value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), where `true` indicates that the key is pressed, and `false` indicates that the key is *not* pressed.

Example
-------

This example logs the `ctrlKey` property when you trigger a `click` event.

### HTML

    <p>Click anywhere to test the <code>ctrlKey</code> property.</p>
    <p id="log"></p>

### JavaScript

    let log = document.querySelector('#log');
    document.addEventListener('click', logKey);

    function logKey(e) {
      log.textContent = `The ctrl key is pressed: ${e.ctrlKey}`;
    }

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-MouseEvent-ctrlKey">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'MouseEvent.ctrlKey' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html">Document Object Model (DOM) Level 2 Events Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-MouseEvent">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'MouseEvent.ctrlKey' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ctrlKey`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`MouseEvent`](../mouseevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/ctrlKey" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/ctrlKey</a>
