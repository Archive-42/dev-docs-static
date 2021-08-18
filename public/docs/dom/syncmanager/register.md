SyncManager.register()
======================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `SyncManager.register` method of the [`SyncManager`](../syncmanager) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a <span class="page-not-created">`SyncRegistration`</span> instance.

Syntax
------

    SyncManager.register([options]).then(function(syncRegistration) { ... })

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to an instance of <span class="page-not-created">`SyncRegistration`</span>.

### Parameters

options <span class="badge inline optional">Optional</span>   
An object that sets options for an instance of <span class="page-not-created">`SyncRegistration`</span>. The available options are:

-   `allowOnBattery`: A boolean that determines whether synchronization is allowed when the user agent is on a battery-powered device. The default is `true`.
-   `id`: The unique identifier of the specified <span class="page-not-created">`SyncRegistration`</span> object.
-   `idleRequired`: A boolean that determines whether synchronization is allowed when the user agent's device is idle. The default is `false`.
-   `maxDelay`: The maximum delay in milliseconds before the next `sync` event (or the first `sync` event if it is periodic). The default is `0`, meaning there is no maximum delay.
-   `minDelay`: The minimum delay in milliseconds before the next `sync` event (or the first sync event if it is periodic). The default is `0`.
-   `minPeriod`: The minimum time in milliseconds between periodic sync events. The default is `0`, meaning events are not periodic.
-   `minRequiredNetwork`: The network condition under which background synchronization will occur. Valid values are `'network-any'`, `'network-offline'`, `'network-online'`, `'network-non-mobile'`. The default value is `'network-online'`.

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

`register`

49

79

No

No

No

No

49

49

No

No

No

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SyncManager/register" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SyncManager/register</a>
