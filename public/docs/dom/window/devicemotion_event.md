Window: devicemotion event
==========================

The `devicemotion` event is fired at a regular interval and indicates the amount of physical force of acceleration the device is receiving at that time. It also provides information about the rate of rotation, if available.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../devicemotionevent"><code>DeviceMotionEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="ondevicemotion"><code>Window.ondevicemotion</code></a></td></tr></tbody></table>

Examples
--------

    function handleMotionEvent(event) {

        var x = event.accelerationIncludingGravity.x;
        var y = event.accelerationIncludingGravity.y;
        var z = event.accelerationIncludingGravity.z;

        // Do something awesome.
    }

    window.addEventListener("devicemotion", handleMotionEvent, true);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/deviceorientation/#devicemotion">DeviceOrientation Event Specification<br />
<span class="small">The definition of 'DeviceMotion event' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td></tr></tbody></table>

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

`devicemotion_event`

Yes

≤18

6

?

Yes

?

Yes

Yes

6

No

4.2

Yes

See also
--------

-   [`deviceorientation`](deviceorientation_event)
-   [DeviceOrientation Event](https://www.w3.org/TR/orientation-event/#devicemotion)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/devicemotion_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/devicemotion_event</a>
