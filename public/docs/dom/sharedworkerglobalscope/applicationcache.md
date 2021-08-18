SharedWorkerGlobalScope.applicationCache
========================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Important**

Application Cache is deprecated as of Firefox 44, and is no longer available in insecure contexts from Firefox 60 onwards ([bug 1354175](https://bugzilla.mozilla.org/show_bug.cgi?id=1354175), currently Nightly/Beta only). Don't use it to make offline websites — consider using [service workers](../service_worker_api) instead.

The `applicationCache` read-only property of the [`SharedWorkerGlobalScope`](../sharedworkerglobalscope) interface returns the <span class="page-not-created">`ApplicationCache`</span> object for the worker (see [Using the application cache](https://developer.mozilla.org/en-US/docs/Web/HTML/Using_the_application_cache)).

Syntax
------

    var nameObj = self.applicationCache;

### Value

An <span class="page-not-created">`ApplicationCache`</span>.

Example
-------

If a shared worker has an AppCache associated with it, you can return a reference to the cache using

    self.applicationCache

from inside the shared worker.

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

-   [`SharedWorkerGlobalScope`](../sharedworkerglobalscope)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope/applicationCache" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SharedWorkerGlobalScope/applicationCache</a>
