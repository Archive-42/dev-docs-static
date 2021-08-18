# DOMPoint

A `DOMPoint` object represents a 2D or 3D point in a coordinate system; it includes values for the coordinates in up to three dimensions, as well as an optional perspective value. `DOMPoint` is based on [`DOMPointReadOnly`](dompointreadonly) but allows its properties' values to be changed.

In general, a positive `x` component represents a position to the right of the origin, a positive `y` component is downward from the origin, and a positive `z` component extends outward from the screen (in other words, toward the user).

## Constructor

[`DOMPoint()`](dompoint/dompoint)  
Creates and returns a new `DOMPoint` object given the values of zero or more of its coordinate components and optionally the `w` perspective value. You can also use an existing `DOMPoint` or `DOMPointReadOnly` or a [`DOMPointInit`](dompointinit) dictionary to create a new point by calling the [`DOMPoint.fromPoint()`](dompoint/frompoint) static method.

## Methods

_`DOMPoint` inherits methods from its parent, [`DOMPointReadOnly`](dompointreadonly)._

## Static methods

[`DOMPoint.fromPoint()`](dompoint/frompoint)  
Creates a new mutable `DOMPoint` object given an existing point (or a [`DOMPointInit`](dompointinit) dictionary) which provides the values for its properties.

## Properties

_`DOMPoint` inherits properties from its parent, [`DOMPointReadOnly`](dompointreadonly)._

[`DOMPoint.x`](dompointreadonly/x)  
The `x` coordinate of the `DOMPoint`.

[`DOMPoint.y`](dompointreadonly/y)  
The `y` coordinate of the `DOMPoint`.

[`DOMPoint.z`](dompointreadonly/z)  
The `z` coordinate of the `DOMPoint`.

[`DOMPoint.w`](dompointreadonly/w)  
The perspective value of the `DOMPoint`.

## Examples

In the [WebXR Device API](webxr_device_api), `DOMPointReadOnly` values are used to represent positions and orientations. In the following snippet, the pose of the XR device (such as a VR headset or phone with AR capabilities) can be retrieved by calling using [`XRFrame.getViewerPose()`](xrframe/getviewerpose) during an [`XRSession`](xrsession) animation frame, then accessing the resulting [`XRPose`](xrpose)'s [`transform`](xrpose/transform) property, which contains two `DOMPointReadOnly` attributes: [`position`](xrrigidtransform/position) as a vector and <span class="page-not-created">`orientation`</span> as a quaternion.

    function onXRFrame(time, xrFrame) {
      let viewerPose = xrFrame.getViewerPose(xrReferenceSpace);

      if (viewerPose) {
        let position = viewerPose.transform.position;
        let orientation = viewerPose.transform.orientation;

        console.log('XR Viewer Position: {x: ' + roundToTwo(position.x)
                                     + ', y: ' + roundToTwo(position.y)
                                     + ', z: ' + roundToTwo(position.z));

        console.log('XR Viewer Orientation: {x: ' + roundToTwo(orientation.x)
                                        + ', y: ' + roundToTwo(orientation.y)
                                        + ', z: ' + roundToTwo(orientation.z)
                                        + ', w: ' + roundToTwo(orientation.w));
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#DOMPoint">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'DOMPoint' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

## Browser compatibility

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

`DOMPoint`

61

79

31

No

48

10.1

61

61

31

45

10.3

8.0

`DOMPoint`

61

79

31

No

48

10.1

61

61

31

45

10.3

8.0

`worker_support`

61

79

69

No

48

10.1

61

61

No

45

10.3

8.0

## See also

- [`DOMRect`](domrect)
- [`DOMMatrix`](dommatrix)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint</a>
