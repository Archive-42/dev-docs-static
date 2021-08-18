StorageManager.persisted()
==========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `persisted()` method of the [`StorageManager`](../storagemanager) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to `true` if box mode is persistent for your site's storage.

Syntax
------

    navigator.storage.persisted().then(function(persistent) { ... })

### Parameters

None.

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

Example
-------

    if (navigator.storage && navigator.storage.persist)
      navigator.storage.persisted().then(function(persistent) {
        if (persistent)
          console.log("Storage will not be cleared except by explicit user action");
        else
          console.log("Storage may be cleared by the UA under storage pressure.");
      });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://storage.spec.whatwg.org/#dom-storagemanager-persisted">Storage<br />
<span class="small">The definition of 'persisted' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`persisted`

52

48-52

≤79

55

No

Yes

No

52

48-52

52

48-52

55

Yes

No

6.0

5.0-6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StorageManager/persisted" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StorageManager/persisted</a>
