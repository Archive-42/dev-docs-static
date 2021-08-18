Permissions API
===============

The **Permissions API** provides a consistent programmatic way to query the status of API permissions attributed to the current context. For example, the Permissions API can be used to determine if permission to access a particular API has been granted or denied.

**Note:** This feature is available in [Web Workers](web_workers_api) (although not current versions of Firefox, as [WorkerNavigator.permissions](workernavigator/permissions) is not implemented).

Concepts and usage
------------------

Historically different APIs handle their own permissions inconsistently — for example the [Notifications API](notifications_api) allows for explicit checking of permission status and requesting permission, whereas the [Geolocation API](geolocation) doesn't (which causes problems if the user denied the initial permission request). The Permissions API provides the tools to allow developers to implement a better user experience as far as permissions are concerned.

The `permissions` property has been made available on the [`Navigator`](navigator) object, both in the standard browsing context and the worker context ([`WorkerNavigator`](workernavigator) — so permission checks are available inside workers), and returns a [`Permissions`](permissions) object that provides access to the Permissions API functionality.

Once you have this object you can then perform permission-related tasks, for example querying a permission using the [`Permissions.query()`](permissions/query) method to return a promise that resolves with the [`PermissionStatus`](permissionstatus) for a specific API.

Not all APIs' permission statuses can be queried using the Permissions API. Notable APIs that are Permissions-aware include:

-   [Clipboard API](clipboard_api)
-   [Notifications API](notifications_api)
-   [Push API](push_api)
-   Web MIDI API

More APIs will gain Permissions API support over time.

Examples
--------

We have made a simple example available called Location Finder. You can [run the example live](https://chrisdavidmills.github.io/location-finder-permissions-api/), or [view the source code on Github](https://github.com/chrisdavidmills/location-finder-permissions-api/tree/gh-pages).

Read more about how it works in our article [Using the Permissions API](permissions_api/using_the_permissions_api).

Interfaces
----------

 [`Navigator.permissions`](navigator/permissions) and [`WorkerNavigator.permissions`](workernavigator/permissions) <span class="badge inline readonly">Read only </span>   
Provides access to the [`Permissions`](permissions) object from the main context and worker context respectively.

[`Permissions`](permissions)  
Provides the core Permission API functionality, such as methods for querying and revoking permissions.

[`PermissionStatus`](permissionstatus)  
Provides access to the current status of a permission, and an event handler to respond to changes in permission status.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/permissions/">Permissions</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Permissions_API`

43

79

46

No

Yes

No

No

See [bug 490120](https://crbug.com/490120)

43

46

Yes

No

4.0

`accelerometer_permission`

62

79

?

No

?

No

No

62

?

?

No

8.0

`accessibility-events_permission`

62

79

?

No

?

No

No

62

?

?

No

8.0

`ambient-light-sensor_permission`

62

79

?

No

?

No

No

62

?

?

No

8.0

`background-sync_permission`

62

79

?

No

?

No

No

62

?

?

No

8.0

`camera_permission`

64

79

?

No

?

No

No

64

?

?

No

9.0

`clipboard-read_permission`

64

79

No

No

?

No

No

64

No

?

No

9.0

`clipboard-write_permission`

64

79

No

No

?

No

No

64

No

?

No

9.0

`geolocation_permission`

43

79

?

No

30

No

No

43

?

30

No

4.0

`gyroscope_permission`

51

79

?

No

?

No

No

51

?

?

No

5.0

`magnetometer_permission`

62

79

?

No

?

No

No

62

?

?

No

8.0

`microphone_permission`

64

79

?

No

?

No

No

64

?

?

No

9.0

`midi_permission`

43

79

?

No

30

No

No

43

?

30

No

4.0

`notifications_permission`

43

79

?

No

30

No

No

43

?

30

No

4.0

`payment-handler_permission`

66

79

?

No

?

No

No

66

?

?

No

9.0

`persistent-storage_permission`

71

79

53

No

58

No

No

71

53

50

No

10.0

`push_permission`

43

79

?

No

30

No

No

43

?

30

No

4.0

`query`

43

79

46

No

Yes

No

No

43

46

Yes

No

4.0

`request`

46

79

No

No

33

No

No

46

No

33

No

No

`requestAll`

48

79

No

No

35

No

No

48

No

35

No

No

`revoke`

46

79

51

47-51

No

33

No

No

46

51

47-51

33

No

No

See also
--------

-   [Using the Permissions API](permissions_api/using_the_permissions_api)
-   [Using the Permissions API to Detect How Often Users Allow or Deny Camera Access](https://blog.addpipe.com/using-permissions-api-to-detect-getusermedia-responses/)
-   [`Notification.permission`](notification/permission)
-   [Privacy, permissions, and information security](https://developer.mozilla.org/en-US/docs/Web/Privacy)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Permissions_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Permissions_API</a>
