PeriodicSyncEvent()
===================

**Draft**

This page is not complete.

The `PeriodicSyncEvent()` constructor creates a new [`PeriodicSyncEvent`](../periodicsyncevent) object. This constructor is not typically used. The browser creates these objects itself and provides them to [`ServiceWorkerGlobalScope.onperiodicsync`](../serviceworkerglobalscope/onperiodicsync) callback.

Syntax
------

    var PeriodicSyncEvent = new PeriodicSyncEvent();

### Parameters

*type*  
A [`DOMString`](../domstring) indicating the event which occurred. For `PeriodicSyncEvent`, this is always `periodicsync`.

 *periodicSyncEventInitDict* <span class="badge inline optional">Optional</span>   
An options object containing any initialization data you want to populate the `PeriodicSyncEvent` object with. The options are:

-   `tag`: The tag referencing the sync event.

### Return value

A [`PeriodicSyncEvent`](../periodicsyncevent) object configured using the given inputs.

Examples
--------

This example constructs a new [`PeriodicSyncEvent`](../periodicsyncevent) with the relevant associated tag.

    var syncTag = {
      tag : 'unique-tag'
    }

    var psEvent = new ExtendableEvent('periodicsync', syncTag);

    psEvent.tag; // should return 'unique-tag'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/periodic-background-sync/#periodicsync-event">Web Periodic Background Synchronization<br />
<span class="small">The definition of 'PeriodicSyncEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PeriodicSyncEvent`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PeriodicSyncEvent/PeriodicSyncEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PeriodicSyncEvent/PeriodicSyncEvent</a>
