InputDeviceCapabilities.firesTouchEvents
========================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `InputDeviceCapabilities.firesTouchEvents` read-only property returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether the device dispatches touch events.

You can use this property to detect mouse events that represent an action that may already have been handled by touch event handlers. This doesn't necessarily mean the device is a touch screen. For example, stylus and mouse devices typically generate touch events on mobile browsers.

Syntax
------

    var boolean = InputDeviceCapabilities.firesTouchEvents

### Returns

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)

Example
-------

    myButton.addEventListener('mousedown', function(e) {
      if (!e.sourceCapabilities.firesTouchEvents)
        myButton.classList.add("pressed");
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/InputDeviceCapabilities/#dom-inputdevicecapabilities-firestouchevents">InputDeviceCapabilities<br />
<span class="small">The definition of 'fireTouchEvents' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`firesTouchEvents`

47

≤79

?

No

Yes

No

47

47

?

Yes

No

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/InputDeviceCapabilities/firesTouchEvents" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/InputDeviceCapabilities/firesTouchEvents</a>
