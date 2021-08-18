InstallEvent.InstallEvent()
===========================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `InstallEvent()` constructor creates a new [`InstallEvent`](../installevent) object.

Syntax
------

    var myInstallEvent = new InstallEvent(type, init);

### Parameters

*type*  
The type of the event.

 *init* <span class="badge inline optional">Optional</span>   
An options object containing any custom settings that you want to apply to the event object. Available options are as follows:

-   `activeWorker`: The [`ServiceWorker`](../serviceworker) that is currently actively controlling the page.

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

`InstallEvent`

40

≤79

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

No

40

40

44

27

No

4.0

See also
--------

-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
-   [Fetch API](../fetch_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/InstallEvent/InstallEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/InstallEvent/InstallEvent</a>
