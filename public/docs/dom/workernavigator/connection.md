WorkerNavigator.connection
==========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `WorkerNavigator.connection` read-only property returns a [`NetworkInformation`](../networkinformation) object containing information about the system's connection, such as the current bandwidth of the user's device or whether the connection is metered. This could be used to select high definition content or low definition content based on the user's connection.

Syntax
------

    connectionInfo = self.navigator.connection

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/netinfo/#connection-attribute">Network Information API<br />
<span class="small">The definition of 'Navigator.connection' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial specification</td></tr></tbody></table>

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

`connection`

61

≤79

No

No

Yes

No

50

38

53

37

No

3.0

See also
--------

-   [Online and offline events](../navigatoronline/online_and_offline_events)
-   [Network Information API](../network_information_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator/connection" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator/connection</a>
