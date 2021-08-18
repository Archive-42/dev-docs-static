XRPermissionDescriptor.mode
===========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `mode` property of the [`XRPermissionDescriptor`](../xrpermissiondescriptor) dictionary is a string taken from the [`XRSessionMode`](../xrsessionmode) enumerated type, specifying which Web XR session mode (`inline`, `immersive-vr`, or `immersive-ar`) the described permissions will be used for.

Syntax
------

    xrPermissionDescriptor = {
      mode: xrSessionMode,
      requiredFeatures: reqFeatureList,
      optionalFeatures: optFeatureList
    };

    xrPermissionDescriptor.mode = xrSessionMode;
    xrMode = xrPermissionDescriptor.mode;

### Value

A [`DOMString`](../domstring) whose value is one of the strings found in the [`XRSessionMode`](../xrsessionmode) enumerated type:

 `immersive-ar` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
The session's output will be given exclusive access to the immersive device, but the rendered content will be blended with the real-world environment. The session's [`environmentBlendMode`](../xrsession/environmentblendmode) indicates the method to be used to blend the content together.

**Important:** The `immersive-ar` mode is defined by the WebXR Augmented Reality Module, which is not yet stable and should not be used other than for testing and experimentation.

`immersive-vr`  
Indicates that the rendered session will be displayed using an immersive XR device in VR mode; it is not intended to be overlaid or integrated into the surrounding environment. The [`environmentBlendMode`](../xrsession/environmentblendmode) is expected to be `opaque` if possible, but might be `additive` if the hardware requires it.

`inline`  
The output is presented inline within the context of an element in a standard HTML document, rather than occupying the full visual space. Inline sessions can be presented in either mono or stereo mode, and may or may not have viewer tracking available. Inline sessions don't require special hardware and should be avalable on any [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) offering WebXR API support.

Usage notes
-----------

Examples
--------

The example below checks to ensure that permission has been granted to allow the user to use WebXR for an immersive virtual reality experience. No specific features are specified during this query; see [`requiredFeatures`](requiredfeatures) and [`optionalFeatures`](optionalfeatures) for more information on specifying features during a WebXR permission check.

    let xrPermissionDesc = {
      name: "xr",
      mode: "immersive-vr"
    };

    if (navigator.permissions) {
      navigator.permissions.query(xrPermissionDesc).then(({state}) => {
        switch(state) {
          case "granted":
            setupXR();
            break;
          case "prompt":
            promptAndSetupXR();
            break;
          default:
            /* do nothing otherwise */
           break;
      }
      .catch(err) {
        console.log(err);
      }
    } else {
      setupXR();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrpermissiondescriptor-mode">WebXR Device API<br />
<span class="small">The definition of 'XRPermissionDescriptor.mode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`mode`

No

No

No

No

No

No

No

No

No

No

No

No

See also
--------

-   [Permissions and security for WebXR](../webxr_device_api/permissions_and_security)
-   [`XRPermissionStatus`](../xrpermissionstatus)
-   [`navigator.permissions`](../navigator/permissions) and [`WorkerNavigator.permissions`](../workernavigator/permissions)
-   [`Permissions`](../permissions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRPermissionDescriptor/mode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRPermissionDescriptor/mode</a>
