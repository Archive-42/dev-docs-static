NetworkInformation
==================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `NetworkInformation` interface provides information about the connection a device is using to communicate with the network and provides a means for scripts to be notified if the connection type changes. The `NetworkInformation` interfaces cannot be instantiated. It is instead accessed through the `connection` property of the [`Navigator`](navigator) interface.

**Note:** This feature is available in [Web Workers](web_workers_api).

Properties
----------

*This interface also inherits properties of its parent, [`EventTarget`](eventtarget).*

 [`NetworkInformation.downlink`](networkinformation/downlink) <span class="badge inline readonly">Read only </span>   
Returns the effective bandwidth estimate in megabits per second, rounded to the nearest multiple of 25 kilobits per seconds.

 [`NetworkInformation.downlinkMax`](networkinformation/downlinkmax) <span class="badge inline readonly">Read only </span>   
Returns the maximum downlink speed, in megabits per second (Mbps), for the underlying connection technology.

 [`NetworkInformation.effectiveType`](networkinformation/effectivetype) <span class="badge inline readonly">Read only </span>   
Returns the effective type of the connection meaning one of 'slow-2g', '2g', '3g', or '4g'. This value is determined using a combination of recently observed round-trip time and downlink values.

 [`NetworkInformation.rtt`](networkinformation/rtt) <span class="badge inline readonly">Read only </span>   
Returns the estimated effective round-trip time of the current connection, rounded to the nearest multiple of 25 milliseconds.

 [`NetworkInformation.saveData`](networkinformation/savedata) <span class="badge inline readonly">Read only </span>   
Returns `true` if the user has set a reduced data usage option on the user agent.

 [`NetworkInformation.type`](networkinformation/type) <span class="badge inline readonly">Read only </span>   
Returns the type of connection a device is using to communicate with the network. It will be one of the following values:

-   `bluetooth`
-   `cellular`
-   `ethernet`
-   `none`
-   `wifi`
-   `wimax`
-   `other`
-   `unknown`

### Event handlers

[`NetworkInformation.onchange`](networkinformation/onchange)  
The event that's fired when connection information changes and the `change` is fired on this object.

Methods
-------

*This interface also inherits methods of its parent, [`EventTarget`](eventtarget).*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/netinfo/#networkinformation-interface">Network Information API<br />
<span class="small">The definition of 'NetworkInformation' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`NetworkInformation`

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

See also
--------

-   [Network Information API](network_information_api)
-   [Online and offline events](navigatoronline/online_and_offline_events)
-   The [`Navigator`](navigator) interface that implements it.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NetworkInformation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NetworkInformation</a>
