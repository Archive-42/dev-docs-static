Network Information API
=======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The Network Information API provides information about the system's connection in terms of general connection type (e.g., 'wifi', 'cellular', etc.). This can be used to select high definition content or low definition content based on the user's connection. The entire API consists of the addition of the [`NetworkInformation`](networkinformation) interface and a single property to the [`Navigator`](navigator) interface: [`Navigator.connection`](navigator/connection).

**Note:** This feature is available in [Web Workers](web_workers_api).

Examples
--------

### Detect connection changes

This example watches for changes to the user's connection.

    var connection = navigator.connection || navigator.mozConnection || navigator.webkitConnection;
    var type = connection.effectiveType;

    function updateConnectionStatus() {
      console.log("Connection type changed from " + type + " to " + connection.effectiveType);
      type = connection.effectiveType;
    }

    connection.addEventListener('change', updateConnectionStatus);

### Preload large resources

The connection object is useful for deciding whether to preload resources that take large amounts of bandwidth or memory. This example would be called soon after page load to check for a connection type where preloading a video may not be desirable. If a cellular connection is found, then the `preloadVideo` flag is set to `false`. For simplicity and clarity, this example only tests for one connection type. A real-world use case would likely use a switch statement or some other method to check all of the possible values of [`NetworkInformation.type`](networkinformation/type). Regardless of the `type` value you can get an estimate of connection speed through the [`NetworkInformation.effectiveType`](networkinformation/effectivetype) property.

    let preloadVideo = true;
    var connection = navigator.connection || navigator.mozConnection || navigator.webkitConnection;
    if (connection) {
      if (connection.effectiveType === 'slow-2g') {
        preloadVideo = false;
      }
    }

Interfaces
----------

[`NetworkInformation`](networkinformation)  
Provides information about the connection a device is using to communicate with the network and provides a means for scripts to be notified if the connection type changes. The `NetworkInformation` interfaces cannot be instantiated. It is instead accessed through the [`Navigator`](navigator) interface.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/netinfo/">Network Information API<br />
<span class="small">The definition of 'Network Information API' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial specification</td></tr></tbody></table>

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

`Network_Information_API`

61

79

Yes

No

Yes

No

50

38

14

The Network API is enabled by default. Can be disabled using the `dom.netinfo.enabled` preference.

37

No

3.0

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

`Network_Information_API`

61

79

No

No

48

No

50

38

31

45

No

3.0

`downlink`

61

79

No

No

48

No

50

38

?

45

No

3.0

`downlinkMax`

61

Only supported in Chrome OS

No

No

No

No

No

50

38

No

45

No

3.0

`effectiveType`

61

79

No

No

48

No

50

38

Yes

45

No

3.0

`onchange`

61

79

No

No

48

No

50

38

No

On Firefox, the event handler property corresponding to the `change` event is `ontypechange`.

45

No

3.0

`ontypechange`

No

No

No

No

?

No

No

38

31

?

No

No

`rtt`

61

79

No

No

48

No

50

38

No

45

No

3.0

`saveData`

65

79

No

No

Yes

No

65

65

?

Yes

No

9.0

`type`

61

Only supported in Chrome OS

No

No

No

No

No

50

38

31

45

No

3.0

`worker_support`

61

79

No

No

48

No

50

38

53

45

No

3.0

BCD tables only load in the browser

### Navigator.connection

BCD tables only load in the browser

See also
--------

-   [Network Information API Specification](https://w3c.github.io/netinfo/)ED
-   [Online and offline events](navigatoronline/online_and_offline_events)
-   [`window.navigator.connection`](navigator/connection)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Network_Information_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Network_Information_API</a>
