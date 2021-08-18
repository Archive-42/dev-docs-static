StorageManager.persist()
========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `persist()` method of the [`StorageManager`](../storagemanager) interface requests permission to use persistent storage, and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to `true` if permission is granted and box mode is persistent, and `false` otherwise.

Syntax
------

    navigator.storage.persist().then(function(persistent) { ... })

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

Example
-------

    if (navigator.storage && navigator.storage.persist)
      navigator.storage.persist().then(function(persistent) {
        if (persistent)
          console.log("Storage will not be cleared except by explicit user action");
        else
          console.log("Storage may be cleared by the UA under storage pressure.");
      });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://storage.spec.whatwg.org/#dom-storagemanager-persist">Storage<br />
<span class="small">The definition of 'persist' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`persist`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StorageManager/persist" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StorageManager/persist</a>
