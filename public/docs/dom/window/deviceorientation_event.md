Window: deviceorientation event
===============================

The `deviceorientation` event is fired when fresh data is available from an orientation sensor about the current orientation of the device as compared to the Earth coordinate frame. This data is gathered from a magnetometer inside the device. See [Orientation and motion data explained](https://developer.mozilla.org/en-US/docs/Web/Events/Orientation_and_motion_data_explained) for details.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../deviceorientationevent"><code>DeviceOrientationEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="ondeviceorientation"><code>window.ondeviceorientation</code></a></td></tr></tbody></table>

Examples
--------

    if (window.DeviceOrientationEvent) {
        window.addEventListener("deviceorientation", function(event) {
            // alpha: rotation around z-axis
            var rotateDegrees = event.alpha;
            // gamma: left to right
            var leftToRight = event.gamma;
            // beta: front back motion
            var frontToBack = event.beta;

            handleOrientationEvent(frontToBack, leftToRight, rotateDegrees);
        }, true);
    }

    var handleOrientationEvent = function(frontToBack, leftToRight, rotateDegrees) {
        // do something amazing
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/deviceorientation/#deviceorientation">DeviceOrientation Event Specification<br />
<span class="small">The definition of 'DeviceOrientation event' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td></tr></tbody></table>

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

`deviceorientation_event`

7

≤18

6

3.6-6

?

12

Yes

3

18

6

4-6

12

4.2

1.0

See also
--------

-   [`devicemotion`](devicemotion_event)
-   [Detecting device orientation](https://developer.mozilla.org/en-US/docs/Web/Events/Detecting_device_orientation)
-   [Orientation and motion data explained](https://developer.mozilla.org/en-US/docs/Web/Events/Orientation_and_motion_data_explained)
-   Simulating orientation events on desktop browsers with the [orientation-devtool](https://louisremi.github.com/orientation-devtool/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/deviceorientation_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/deviceorientation_event</a>
