SyncManager.getTags()
=====================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `SyncManager.getTags` method of the [`SyncManager`](../syncmanager) interface returns a list of developer-defined identifiers for `SyncManager` registrations.

Syntax
------

    SyncManager.getTags().then(function(tags[]) { ... })

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to an array of <span class="page-not-created">`DOMString`</span>s containing developer-defined identifiers for `SyncManager` registrations.

### Parameters

None.

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

`getTags`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SyncManager/getTags" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SyncManager/getTags</a>
