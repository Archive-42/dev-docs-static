Touch.force
===========

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Touch.force` read-only property returns the amount of pressure the user is applying to the touch surface for a [`Touch`](../touch) point.

Syntax
------

    touchItem.force;

### Return value

A `float` that represents the amount of pressure the user is applying to the touch surface. This is a value between `0.0` (no pressure) and `1.0` (the maximum amount of pressure the hardware can recognize). A value of `0.0` is returned if no value is known (for example the touch device does not support this property). In environments where force is known, the absolute pressure represented by the force attribute, and the sensitivity in levels of pressure, may vary.

Example
-------

This example illustrates using the [`Touch`](../touch) interface's [`Touch.force`](force) property. This property is a relative value of pressure applied, in the range `0.0` to `1.0`, where `0.0` is no pressure, and `1.0` is the highest level of pressure the touch device is capable of sensing.

In following code snippet, the `touchstart` event handler iterates through the `targetTouches` list and logs the `force` value of each touch point but the code could invoke different processing depending on the value.

    someElement.addEventListener('touchstart', function(e) {
       // Iterate through the list of touch points and log each touch
       // point's force.
       for (var i=0; i < e.targetTouches.length; i++) {
         // Add code to "switch" based on the force value. For example
         // minimum pressure vs. maximum pressure could result in
         // different handling of the user's input.
         console.log("targetTouches[" + i + "].force = " + e.targetTouches[i].force);
       }
    }, false);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/touch-events/#dom-touch-force">Touch Events – Level 2</a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`force`

Yes

≤79

Yes

No

Yes

No

Yes

Yes

Yes

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Touch/force" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Touch/force</a>
