Window.applicationCache
=======================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Important**

Application Cache is deprecated as of Firefox 44, and is no longer available in insecure contexts from Firefox 60 onwards ([bug 1354175](https://bugzilla.mozilla.org/show_bug.cgi?id=1354175), currently Nightly/Beta only). Don't use it to offline websites — consider using [service workers](../service_worker_api) instead.

Returns a reference to the application cache object for the window.

Syntax
------

    cache = window.applicationCache

### Parameters

-   `cache` is an object reference to an `OfflineResourceList`.

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

`applicationCache`

4

79

29

No

10.6

No

Yes

Yes

29

Yes

?

Yes

See also
--------

-   [Using Application Cache](https://developer.mozilla.org/en-US/docs/Web/HTML/Using_the_application_cache)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/applicationCache" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/applicationCache</a>
