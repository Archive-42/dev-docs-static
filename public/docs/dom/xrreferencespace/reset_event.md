XRReferenceSpace: reset event
=============================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `reset` event is sent to an [`XRReferenceSpace`](../xrreferencespace) object when a discontinuity is detected in either the native origin or the effective origin, causing a jump in the position or orientation of objects oriented using the reference space. This is common when the user calibrates or recalibrates an XR device, or if the device automatically changes its origin after losing tracking of the user, then re-gaining it.

In the case of [`XRBoundedReferenceSpace`](../xrboundedreferencespace) objects, the `reset` event can also be fired when the [`boundsGeometry`](../xrboundedreferencespace/boundsgeometry) changes.

In either case, the event is sent before any WebXR animation frames which make use of the new origin are executed.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../xrreferencespaceevent"><code>XRReferenceSpaceEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onreset"><code>onreset</code></a></td></tr></tbody></table>

Usage notes
-----------

The `reset` event indicates that the coordinate system has been reset or reconfigured by changing the reference space's origin, moving and rotating it as indicated by the event's [`transform`](../xrreferencespaceevent/transform) property. The event is sent before any animation frame callbacks are executed to render the pending frame, to ensure that those callbacks have the updated coordinate system available.

There are a number of reasons why a reset might occur. Most common among them are the following:

-   The user has manually reset the coordinate system, such as by requesting that the headset recalibrate itself to ensure that the facing direction and hand controllers are synchronized with the user's actual position and facing. This is primarily an issue for `local` or `local-floor` reference spaces.
-   For a `bounded-floor` reference space, the coordinate system can be reset if the user exits the boundaries of the reference space and enters a new one (such as by crossing from one level to another in a game, where each level is its own map with its own coordinate system).
-   The tracking system has temporarily lost the user, then regained them, but not until after they had moved enough to leave the immediate vicinity of the last-known position. Primarily an issue for `unbounded` reference spaces.
-   The user is in an `unbounded` reference space and has moved far enough from the starting position (the reference space's origin) that floating-point or other forms of error or drift are problematic. The coordinate system is thus reset with its new origin at or near the user's current position.
-   The WebXR infrastructure or hardware drivers detected that the device had temporarily lost tracking, causing the hardware and software to be out of sync on position and orientation.

**Note:** A `reset` event will *not* occur if the reference space is able to regain tracking of its previous origin, since that means the origin has not been forced to be relocated. This event is only fired when the origin has to be relocated to recover from the tracking loss.

### Manual resets

If you've spent any time using a VR headset, you've had times when you've started it up and although you're facing straight ahead, the headset thinks you're looking at the sky or the floor; or times when you point the hand controller straight forward, but it thinks you're pointing it up and to the right somewhere. When that happens, you typically hold down a button somewhere and it causes the world to resynchronize to the device's current orientation. That works by sending a \`reset\` event to the reference space or reference spaces that are based on the headset's orientation.

### Handling discontinuities

You can handle jumps in the viewer's position by watching the Boolean [`XRPose`](../xrpose) property [`emulatedPosition`](../xrpose/emulatedposition). If a jump in the viewer's position coincides with `emulatedPosition` toggling from `true` to `false`, the viewer has regained tracking, and that their new position represents a correction from the previously emulated values. This is typically the desired behavior if your site or app doesn't simulate motion through the space by expressly changing the position and/or orientation of the viewer (rather than the user's physical movements being used by the XR device to introduce movement).

However, if that kind of "teleportation" is being used, you actually want to avoid jumping the user's position after tracking recovery, this can introduce additional and potentially jarring jumping. Instead of allowing this to happen, you can integrate the `emulatedPosition` into the teleportation offset calculated prior to calling [`getOffsetReferenceSpace()`](getoffsetreferencespace) to create a new reference space whose updated effective origin is adjusted by the distance the viewer's position jumped since the previous frame. This way, the user's position only changes once rather than twice.

### The effect of discontinuity size

The `reset` event won't be fired when the discontinuity is small enough that the device is able to regain tracking within the same tracking area. Nor will be fired at an unbounded reference space as it makes small adjustments to its native origin over time to maintain the space's stability in the vicinity of the user; only large discontinuities will trigger a reset.

Examples
--------

To add a handler for the `reset` event, you can use either of two approaches. First, you can use the [`addEventListener()`](../eventtarget/addeventlistener) method:

    viewerRefSpace.addEventListener("reset", (event) => {
      /* perform reset related tasks */
    });

The second option is to set the `XRReferenceSpace` object's [`onreset`](onreset) event handler property:

    viewerRefSpace.onreset = (event) => {
      /* perform reset related tasks */
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#eventdef-xrreferencespace-reset">WebXR Device API<br />
<span class="small">The definition of 'reset event' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpace/reset_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpace/reset_event</a>
