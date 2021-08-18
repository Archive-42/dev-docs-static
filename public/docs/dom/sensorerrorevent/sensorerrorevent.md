SensorErrorEvent.SensorErrorEvent()
===================================

The `SensorErrorEvent` constructor creates a new [`SensorErrorEvent`](../sensorerrorevent) object which provides information about errors thrown by any of the interfaces based on [`Sensor`](../sensor).

Syntax
------

    sensorErrorEvent = new SensorErrorEvent(type, {error: domException});

### Parameters

*type*  
Will always be `'SensorErrorEvent'`.

 *options* <span class="badge inline optional">Optional</span>   
Currently only one option is supported:

-   `error`: An instance of <span class="page-not-created">`DOMException`</span>.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/generic-sensor/#dom-sensorerrorevent-sensorerrorevent">Generic Sensor API<br />
<span class="small">The definition of 'SensorErrorEvent' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`SensorErrorEvent`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SensorErrorEvent/SensorErrorEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SensorErrorEvent/SensorErrorEvent</a>
