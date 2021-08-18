XRView.eye
==========

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`XRView`](../xrview) interface's read-only `eye` property is a string taken from the [`XREye`](../xreye) enumerated type, indicating which eye's viewpoint the `XRView` represents: `left` or `right`. For views which represent neither eye, such as monoscopic views, this property's value is `none`.

Syntax
------

    let eye = xrView.eye;

### Value

A [`DOMString`](../domstring) whose value is one of the strings enumerated by the [`XREye`](../xreye) type:

`left`  
The [`XRView`](../xrview) represents the point-of-view of the viewer's left eye.

`right`  
The view represents the viewer's right eye.

`none`  
The `XRView` describes a monoscopic view, or the view otherwise doesn't represent a particular eye's point-of-view.

Usage notes
-----------

The primary purpose of this property is to allow the correct area of any pre-rendered stereo content to be presented to the correct eye. For dynamically-rendered 3D content, you can usually ignore this and render each of the viewer's views, one after another.

Examples
--------

This code, from the viewer pose's renderer, iterates over the pose's views and renders them. *However*, we have flags which, if `true`, indicate that a particular eye has been injured during gameplay. When rendering that eye, if the flag is `true`, that view is skipped instead of being rendered.

    glLayer = xrSession.renderState.baseLayer;
    gl.bindFramebuffer(gl.FRAMEBUFFER, glLayer.framebuffer);
    gl.clearColor(0,0, 0, 1.0);
    gl.clearDepth(1.0);
    gl.clear(gl.COLOR_BUFFER_BIT, gl.DEPTH_BUFFER_BIT);

    for (let view of xrPose.views) {
      let skipView = false;

      if (view.eye == "left" && body.leftEye.injured) ||
        skipView = updateInjury(body.leftEye);
      } else if (view.eye == "right" && body.rightEye.injured) {
        skipView = updateInjury(body.rightEye);
      }

      if (!skipView) {
        let viewport = glLayer.getViewport(view);
        gl.viewport(viewport.x, viewport.y, viewport.width, viewport.height);
        renderScene(gl, view);
      }
    }

For each of the views, the value of `eye` is checked and if it's either `left` or `right`, we check to see if the `body.leftEye.injured` or `body.rightEye.injured` property is `true`; if so, we call a function `updateInjury()` on that eye to do things such as allow a bit of healing to occur, track the progress of a poison effect, or the like, as appropriate for the game's needs.

`updateInjury()` returns `true` if the eye is still injured or `false` if the eye has been restored to health by the function,. If the result is `false`, indicating that the eye is now healthy, we render the scene for that eye. Otherwise, we don't.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrview-eye">WebXR Device API<br />
<span class="small">The definition of 'XRView.eye' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`eye`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRView/eye" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRView/eye</a>
