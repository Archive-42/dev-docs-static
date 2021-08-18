ServiceWorkerGlobalScope.onsync
===============================

The `ServiceWorkerGlobalScope.onsync` event of the [`ServiceWorkerGlobalScope`](../serviceworkerglobalscope) interface is<span style="line-height: 1.5;"> fired whenever a </span>`SyncEvent`<span style="line-height: 1.5;"> event occurs. This is triggered when a call to </span>[`SyncManager.register`](../syncmanager/register)<span style="line-height: 1.5;"> is made from a service worker client page. The attempt to sync is made either immediately if the network is available or as soon as the network becomes available. </span>

Syntax
------

    ServiceWorkerGlobalScope.onsync = function(SyncEvent) { ... }
    self.addEventListener('sync', function(SyncEvent) { ... })

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-sync/spec/#dom-serviceworkerglobalscope-onsync">Web Background Synchronization</a></td></tr></tbody></table>

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

`onsync`

49

≤79

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

24

11.1

49

49

44

24

11.3

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/onsync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/onsync</a>
