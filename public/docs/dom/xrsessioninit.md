XRSessionInit
=============

**Draft**

This page is not complete.

The [WebXR Device API](webxr_device_api) dictionary `XRSessionInit` specifies required and/or optional features when requesting a new [`XRSession`](xrsession) by calling the [`navigator.xr.requestSession()`](xrsystem/requestsession) method.

Properties
----------

The following parameters are all optional. If none are included, the device will use [a default feature configuration](#default_features) for all options.

 `optionalFeatures` <span class="badge inline optional">Optional</span>   
An array of values identifying features which the returned [`XRSession`](xrsession) may optionally support. At this time, all features are identified using strings from the [`XRReferenceSpaceType`](xrreferencespacetype) enumeration, but future updates to the WebXR standard may add more features.

 `requiredFeatures` <span class="badge inline optional">Optional</span>   
An array of values which the returned `XRSession` *must* support. These values currently must come from the enumerated type `XRReferenceSpaceType`. More features may be added in future updates to the WebXR standard.

Default features
----------------

### Immersive sessions

All immersive (both `immersive-vr` and `immersive-ar`) sessions support both the `viewer` and `local` reference spaces.

Because immersive sessions are required to support the `local` reference space, any request to open an immersive [`XRSession`](xrsession) is required to obtain [explicit or implicit user consent](webxr_device_api#user_intent).

### Inline sessions

All `inline` WebXR sessions support the `viewer` reference space.

Security requirements
---------------------

Each reference space or feature type has minimum safety requirements. By session type, those are:

<table><thead><tr class="header"><th>Reference space type</th><th>User consent rquirement</th><th>Feature policy requirement</th></tr></thead><tbody><tr class="odd"><td><code>bounded-floor</code></td><td>Always required</td><td><code>xr-spatial-tracking</code></td></tr><tr class="even"><td><code>local</code></td><td>Always required for inline sessions</td><td><code>xr-spatial-tracking</code></td></tr><tr class="odd"><td><code>local-floor</code></td><td>Always required</td><td><code>xr-spatial-tracking</code></td></tr><tr class="even"><td><code>unbounded</code></td><td>Always required</td><td><code>xr-spatial-tracking</code></td></tr><tr class="odd"><td><code>viewer</code></td><td>Always required</td><td>—</td></tr></tbody></table>

See also
--------

-   [Spatial tracking in WebXR](webxr_device_api/spatial_tracking)
-   [`XRSession`](xrsession)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSessionInit" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSessionInit</a>
