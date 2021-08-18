XRHandedness
============

The WebXR enumerated type `XRHandedness` provides values which identify which of a user's hands is being used to operate a particular input controller attached to the XR input device being used. `XRHandedness` is used as the value of the the [`XRInputSource`](xrinputsource) property [`handedness`](xrinputsource/handedness).

Values
------

`none`  
The input controller is not associated with one of the user's hands.

`left`  
The input controller is being held in, worn on, or is attached to the user's left hand.

`right`  
The input controller is being held in, worn on, or is attached to the user's right hand.

Examples
--------

One important usage scentario for `handedness` is to determine which hand a controller is in so you can draw a representation of that hand (or the device that hand is controlling) in virtual space.

    function updateInputSources(session, frame, refSpace) {
      for (let source of session.inputSources) {
        if (source.gripSpace) {
          let gripPose = frame.getPose(source.gripSpace, refSpace);

          if (gripPose) {
            myRenderHandObject(gripPose, inputSource.handedness);
          }
        }
      }
    }

This function, which would be called every animation frame (or possibly just periodically, depending on the degree of smoothness required and any performance constraints), scans the list of input sources looking for any which have a [`gripSpace`](xrinputsource/gripspace) which isn't `null`. If a `gripSpace` is present, that means the input source is a hand-held device of some sort, so it should be rendered visibly if possible.

If `gripSpace` is non-`null`, the function proceeds to get the pose for the `gripSpace` transformed into the current reference space. Assuming that's then valid, a function called `myRenderHandObject()` is called with the grip's pose and the value of `handedness`. With these values in hand (no pun intended), `myRenderHandObject()` can draw the appropriate model positioned and formed for the correct hand.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#enumdef-xrhandedness">WebXR Device API<br />
<span class="small">The definition of 'XRHandedness' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.XRHandedness`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [WebXR Device API](webxr_device_api)
-   [Inputs and input sources](webxr_device_api/inputs)
-   [Using gamepads in WebXR applications](https://developer.mozilla.org/en-US/docs/Web/WebXR%20Device%20API/Gamepads)
-   [`XREye`](xreye): Indicates which eye a view should be displayed for

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRHandedness" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRHandedness</a>
