ServiceWorkerContainer.onerror
==============================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `onerror` property of the [`ServiceWorkerContainer`](../serviceworkercontainer) interface is an event handler fired whenever an `error` event occurs in the associated service workers.

Syntax
------

    serviceWorkerContainer.onerror = function(errorevent) { ... }

Example
-------

    navigator.serviceWorker.onerror = function(errorevent) {
      console.log(`received error message: ${errorevent.message}`);
    }

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

`onerror`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

11.3

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer/onerror" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer/onerror</a>
