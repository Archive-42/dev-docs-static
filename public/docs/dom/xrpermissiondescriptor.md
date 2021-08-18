XRPermissionDescriptor
======================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

User permissions in the [WebXR Device API](webxr_device_api) are managed using the [Permissions API](permissions_api). To that end, the `XRPermissionDescriptor` dictionary is used to describe the WebXR features the app needs to use, as well as those features it would like ot use if permision is granted.

The `XRPermissionDescriptor`'s <span class="page-not-created">`name`</span> must be set to `xr` in order to direct the Permissions API to correctly handle the request as applying to WebXR.

Properties
----------

In addition to inheriting the properties of the parent interface, <span class="page-not-created">`PermissionDescriptor`</span>, `XRPermissionDescriptor` provides the following properties.

 [`mode`](xrpermissiondescriptor/mode)   
An [`XRSessionMode`](xrsessionmode) value indicating the XR mode (`inline`, `immersive-vr`, or `immersive-ar`) for which the permissions are requested.

[`optionalFeatures`](xrpermissiondescriptor/optionalfeatures)  
An array of strings, each specifying the name of a WebXR feature which is requested but not required for the app to function. The available features are the same as those used by [`XRSessionInit`](xrsessioninit); see [Default features](xrsessioninit#default_features) in [XRSessionInit](xrsessioninit) for further information.

[`requiredFeatures`](xrpermissiondescriptor/requiredfeatures)  
An array of strings giving the names of the [WebXR features](xrsessioninit#default_features) for which permission *must* be obtained in order to use your app or site.

Examples
--------

The example below demonstrates performing the permission request for an application that requires the `local-floor` reference space in an `immersive-vr` environment.

If the [Permissions API](permissions_api) is found to be available (by checking to see if [`navigator.permissions`](navigator/permissions) is defined), its [`query()`](permissions/query) method is called, specifying the permission descriptor we've established, `xrPermissionDesc`.

When the returned [promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) resolves, we check the returned status. If permission has been granted, we call a function `setupXR()` that handles preparing the WebXR environment for use. If permission is conditional based on prompting, we call a function `promptAndSetupXR()` that would handle asking for permission before enabling and starting up the environment. And for any other returned state—which is almost certainly `denied`, which is the only other option as of this article's writing—we do nothing, since we can't use WebXR.

If the permission request promise is rejected, the error is handled (currently by just dumping it to the console using domxref("console.log()")}}).

If the Permissions API isn't available at all, this example assumes that WebXR will report an appropriate error if permission isn't available, and tries to start up the WebXR session using the same `setupXR()` function called by the `granted` case.

    let xrPermissionDesc = {
      name: "xr",
      mode: "immersive-vr",
      requiredFeatures: [ "local-floor" ]
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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dictdef-xrpermissiondescriptor">WebXR Device API<br />
<span class="small">The definition of 'XRPermissionDescriptor' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XRPermissionDescriptor`

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

`optionalFeatures`

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

`requiredFeatures`

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

-   [Permissions and security for WebXR](webxr_device_api/permissions_and_security)
-   [`XRPermissionStatus`](xrpermissionstatus)
-   [`navigator.permissions`](navigator/permissions) and [`WorkerNavigator.permissions`](workernavigator/permissions)
-   [`Permissions`](permissions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRPermissionDescriptor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRPermissionDescriptor</a>
