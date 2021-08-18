XRReferenceSpace
================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The WebXR Device API's `XRReferenceSpace` interface describes the coordinate system for a specific tracked entity or object within the virtual world using a specified tracking behavior. The tracking behavior is defined by the selected [reference space type](#Reference_space_types). It expands upon the base class, [`XRSpace`](xrspace), by adding support for several different tracking behaviors as well as to request a new reference space which describes the offset transform between the tracked object and another location in the world.

All reference spaces—with the sole exception being bounded reference spaces—are described using the `XRReferenceSpace` type. Bounded spaces are implemented as [`XRBoundedReferenceSpace`](xrboundedreferencespace) objects. These are special spaces which let you establish a perimeter within which it's "safe" for the viewer to move. For XR systems that allow the user to physically move around, such as those that track movement with a real-world camera, this boundary establishes the edges of the area the user is able to move around in, whether due to physical obstacles or due to limitations of the XR hardware. See the article [Using bounded reference spaces to protect the viewer](webxr_device_api/bounded_reference_spaces) for more on using boundaries to keep the user from colliding with obstacles both physical and virtual.

Properties
----------

*In addition to the properties inherited from [`XRSpace`](xrspace) (of which there are none at this time), `XRReferenceSpace` also inherits the properties of [`EventTarget`](eventtarget). `XRReferenceSpace` defines no additional properties.*

Methods
-------

*In addition to the methods inherited from its parent interface, [`XRSpace`](xrspace) (there are none at this time), `XRReferenceSpace` inherits methods from [`EventTarget`](eventtarget). `XRReferenceSpace` also provides the following methods.*

[`getOffsetReferenceSpace()`](xrreferencespace/getoffsetreferencespace)  
Creates and returns a new reference space object as the same type as the one on which you call the method (so, either `XRReferenceSpace` or [`XRBoundedReferenceSpace`](xrboundedreferencespace)). The new reference space can be used to transform a coordinate from the reference space of the object on which the method is called into a different coordinate space. This is useful for positioning objects while rendering, and to perform the needed transforms when changing the viewer's position and/or orientation in 3D space.

Events
------

*In addition to other events that may be sent to [`XRSpace`](xrspace) or [`EventTarget`](eventtarget) objects, the following also apply to `XRReferenceSpace` objects.*

[`reset`](xrreferencespace/reset_event)  
The `reset` event is sent to an [`XRReferenceSpace`](xrreferencespace) object when the browser detects a discontinuity has occurred wherein the tracked object's origin relative to the user's environment or location. This can happen, for example, after the user recalibrates their XR device, or if the device automatically adjusts its origin after losing and regaining tracking.

In addition to using [`addEventListener()`](eventtarget/addeventlistener), you can establish a `reset` event handler by setting the [`onreset`](xrreferencespace/onreset) event handler property.

Reference space types
---------------------

The reference space returned by [`XRSession.requestReferenceSpace()`](xrsession/requestreferencespace) is either [`XRReferenceSpace`](xrreferencespace) or [`XRBoundedReferenceSpace`](xrboundedreferencespace). The "Interface" column in the table below indicates which of the two types is returned for each reference space type constant..

### Reference space descriptors

The types of reference space are listed in the table below, with brief information about their use cases and which interface is used to implement them.

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>XRReferenceSpaceType</th><th>Description</th><th>Interface</th></tr></thead><tbody><tr class="odd"><td><span id="bounded-floor"><code>bounded-floor</code></span></td><td>Similar to the <code>local</code> type, except the user is not expected to move outside a predetermined boundary, given by the <a href="xrboundedreferencespace/boundsgeometry"><code>boundsGeometry</code></a> in the returned object.</td><td><a href="xrboundedreferencespace"><code>XRBoundedReferenceSpace</code></a></td></tr><tr class="even"><td><span id="local"><code>local</code></span></td><td><p>A tracking space whose native origin is located near the viewer's position at the time the session was created. The exact position depends on the underlying platform and implementation. The user isn't expected to move much if at all beyond their starting position, and tracking is optimized for this use case.</p><p>For devices with six degrees of freedom (6DoF) tracking, the <code>local</code> reference space tries to keep the origin stable relative to the environment.</p></td><td><a href="xrreferencespace"><code>XRReferenceSpace</code></a></td></tr><tr class="odd"><td><span id="local-floor"><code>local-floor</code></span></td><td>Similar to the <code>local</code> type, except the starting position is placed in a safe location for the viewer to stand, where the value of the y axis is 0 at floor level. If that floor level isn't known, the <a href="https://developer.mozilla.org/en-US/docs/Glossary/User_agent">user agent</a> will estimate the floor level. If the estimated floor level is non-zero, the browser is expected to round it such a way as to avoid fingerprinting (likely to the nearest centimeter).</td><td><a href="xrreferencespace"><code>XRReferenceSpace</code></a></td></tr><tr class="even"><td><span id="unbounded"><code>unbounded</code></span></td><td>A tracking space which allows the user total freedom of movement, possibly over extremely long distances from their origin point. The viewer isn't tracked at all; tracking is optimized for stability around the user's current position, so the native origin may drift as needed to accommodate that need.</td><td><a href="xrreferencespace"><code>XRReferenceSpace</code></a></td></tr><tr class="odd"><td><span id="viewer"><code>viewer</code></span></td><td>A tracking space whose native origin tracks the viewer's position and orientation. This is used for environments in which the user can physically move around, and is supported by all instances of <a href="xrsession"><code>XRSession</code></a>, both immersive and inline, though it's most useful for inline sessions. It's particularly useful when determining the distance between the viewer and an input, or when working with offset spaces. Otherwise, typically, one of the other reference space types will be used more often.</td><td><a href="xrreferencespace"><code>XRReferenceSpace</code></a></td></tr></tbody></table>

Usage notes
-----------

### Creating an XRReferenceSpace

There are two situations in which you need to obtain an `XRReferenceSpace`. The first is when you set up your scene and need to obtain a reference space to represent the user's viewpoint on the world for the duration of the [`XRSession`](xrsession). To do that, call the [`XRSession`](xrsession) method [`requestReferenceSpace()`](xrsession/requestreferencespace), specifying the [reference space type](xrreferencespacetype) you wish to obtain.

    xrSession.requestReferenceSpace("local").then((refSpace) => {
      xrReferenceSpace = refSpace;
      /* ... */
    });

The other situation in which you may need to acquire a new reference space is if you need to move the origin to a new position; this is commonly done, for example, when your project allows the user to move through the environment using input devices such as the keyboard, mouse, touchpad, or game controls that are not connected through the XR device. Since the origin will typically be the user's location in the space, you need to change the origin to reflect their movement and any orientation changes they make.

To move or rotate the user's view of the world, you need to change the `XRReferenceSpace` used to represent that viewpoint. However, `XRReferenceSpace` is immutable, so you need to instead create a new reference space representing the changed viewpoint. This is easily done using the [`getOffsetReferenceSpace()`](xrreferencespace/getoffsetreferencespace) method.

    let offsetTransform = new XRRigidTransform({x: 2, y: 0, z: 1},
                                               {x: 0, y: 1, z: 0, w: 1});
    xrReferenceSpace = xrReferenceSpace.getOffsetReferenceSpace(offsetTransform);

This replaces the `XRReferenceSpace` with a new one whose origin and orientation are adjusted to place the new origin at (2, 0, 1) relative to the current origin and rotated given a unit [quaternion](https://developer.mozilla.org/en-US/docs/Glossary/Quaternion) that orients the space to put the viewer facing straight up relative to the previous world orientation.

### Geometry

The native origin of any `XRReferenceSpace` is always configured so that +X is considered to be to the right, +Y is upward, and +Z is "backward" or toward the user.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#xrreferencespace-interface">WebXR Device API<br />
<span class="small">The definition of 'XRReferenceSpace' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XRReferenceSpace`

79

79

No

No

No

No

No

79

No

No

No

11.2

`getOffsetReferenceSpace`

79

79

No

No

No

No

No

79

No

No

No

11.2

`onreset`

79

79

No

No

No

No

No

79

No

No

No

11.2

`reset_event`

79

79

No

No

No

No

No

79

No

No

No

11.2

See also
--------

-   [Fundamentals of WebXR](webxr_device_api/fundamentals)
-   [Geometry and reference spaces in WebXR](webxr_device_api/geometry)
-   [Viewpoints and viewers: Simulating cameras in WebXR](webxr_device_api/cameras)
-   [Matrix math for the web](webgl_api/matrix_math_for_the_web)
-   [Movement, orientation, and motion](webxr_device_api/movement_and_motion)
-   [Using bounded reference spaces to protect the user](webxr_device_api/bounded_reference_spaces)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpace" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpace</a>
