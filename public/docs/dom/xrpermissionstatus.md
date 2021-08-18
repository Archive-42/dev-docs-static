XRPermissionStatus
==================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Draft**

This page is not complete.

The `XRPermissionStatus` interface defines the object returned by calling [`navigator.permissions.query()`](permissions/query) for the `xr` permission name; it indicates whether or not the app or site has permission to use WebXR, an may be monitored over time for changes to that permissions tate.

Properties
----------

*In addition to the properties listed below, `XRPermissionStatus` includes the properties defined by its parent interface, [`PermissionStatus`](permissionstatus).*

[`granted`](xrpermissionstatus/granted)  
An array of strings listing the names of the features for which permission has been granted as of the time at which `navigator.permissions.query()` was called. Any feature which was specified in either the [`optionalFeatures`](xrpermissiondescriptor/optionalfeatures) or [`requiredFeatures`](xrpermissiondescriptor/requiredfeatures) when calling `navigator.permissions.query()` are listed in `granted` if and only if permission to use them is granted.

Methods
-------

*No methods are defined by `XRPermissionStatus`.*

Usage notes
-----------

Examples
--------

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#xrpermissionstatus">WebXR Device API<br />
<span class="small">The definition of 'XRPermissionStatus' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XRPermissionStatus`

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

`granted`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRPermissionStatus" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRPermissionStatus</a>
