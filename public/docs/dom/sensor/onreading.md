Sensor.onreading
================

The `onreading` [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) is called when a reading is taken on one of the child interfaces of the [`Sensor`](../sensor) interface.

Syntax
------

    sensorInstance.onreading = function
    sensorInstance.addEventListener('reading', function() { ... })

Because [`Sensor`](../sensor) is a base class, `onreading` may only be used on one of its derived classes.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/generic-sensor/#dom-sensor-onreading">Generic Sensor API<br />
<span class="small">The definition of 'onreading' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onreading`

67

79

No

No

54

No

67

67

No

48

No

9.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Sensor/onreading" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Sensor/onreading</a>
