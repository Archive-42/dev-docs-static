TouchEvent.altKey
=================

Summary
-------

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value indicating whether or not the alt (Alternate) key is enabled when the touch event is created. If the alt key is enabled, the attribute's value is `true`. Otherwise, it is `false`.

This property is <span class="badge inline readonly">Read only </span>.

Syntax
------

    var altEnabled = touchEvent.altKey;

### Return value

`altEnabled`  
`true` if the alt key is enabled for this event; and `false` if the alt is not enabled.

Example
-------

This example illustrates how to access the [`TouchEvent`](../touchevent) key modifier properties: [`TouchEvent.altKey`](altkey), [`TouchEvent.ctrlKey`](ctrlkey), [`TouchEvent.metaKey`](metakey) and [`TouchEvent.shiftKey`](shiftkey).

In following code snippet, the `touchstart` event handler logs the state of the event's modifier keys.

    someElement.addEventListener('touchstart', function(e) {
       // Log the state of this event's modifier keys
       console.log("altKey = " + e.altKey);
       console.log("ctrlKey = " + e.ctrlKey);
       console.log("metaKey = " + e.metaKey);
       console.log("shiftKey = " + e.shiftKey);
    }, false);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/touch-events/#dom-touchevent-altkey">Touch Events – Level 2</a></td><td><span class="spec-draft">Draft</span></td><td>Non-stable version.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/touch-events/#widl-TouchEvent-altKey">Touch Events</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`altKey`

22

≤18

52

18-24

No

Yes

No

≤37

Yes

6

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TouchEvent/altKey" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TouchEvent/altKey</a>
