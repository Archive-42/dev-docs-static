PeriodicSyncEvent.tag
=====================

**Draft**

This page is not complete.

The `tag` read-only property of the [`PeriodicSyncEvent`](../periodicsyncevent) interface returns the developer-defined identifier for the [`PeriodicSyncEvent`](../periodicsyncevent). This is specified when calling the [`PeriodicSyncManager.register()`](../periodicsyncmanager/register) method of the [`PeriodicSyncManager`](../periodicsyncmanager) interface. Multiple tags can be used by the web app to run different periodic tasks at different frequencies.

Syntax
------

    const tag = PeriodicSyncEvent.tag;

### Value

Returns a [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) of the defined identifier.

Examples
--------

The following example demonstrates listening for a periodic sync event in the service worker, and accessing the `tag` property.

    self.addEventListener('periodicsync', event => {
      console.log(event.tag); // logs the events tag
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/periodic-background-sync/#dom-periodicsyncevent-tag">Web Periodic Background Synchronization<br />
<span class="small">The definition of 'tag' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`tag`

80

80

No

No

67

No

80

80

No

57

No

13.0

See also
--------

-   [Richer offline experiences with the Periodic Background Sync API](https://web.dev/periodic-background-sync/)
-   [A Periodic Background Sync demo app](https://webplatformapis.com/periodic_sync/periodicSync_improved.html)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PeriodicSyncEvent/tag" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PeriodicSyncEvent/tag</a>
