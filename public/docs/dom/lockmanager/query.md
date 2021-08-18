LockManager.query()
===================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `query()` method of the [`LockManager`](../lockmanager) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves with an object containing information about held and pending locks.

Syntax
------

    var promise<LockManagerSnapshot> = LockManager.query()

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a `LockManagerSnapshot` containing the following properties.

-   `held`: An array of [`Lock`](../lock) objects for held locks.
-   `pending`: An array of [`Lock`](../lock) objects for pending lock requests.

Example
-------

    const state = await navigator.locks.query();
    for (const lock of state.held) {
      console.log(`held lock: name ${lock.name}, mode ${lock.mode}`);
    }
    for (const request of state.pending) {
      console.log(`requested lock: name ${request.name}, mode ${request.mode}`);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/web-locks/#dom-lockmanager-query">Web Locks API<br />
<span class="small">The definition of 'query()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`query`

69

≤79

?

No

56

No

69

69

?

48

No

10.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/LockManager/query" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/LockManager/query</a>
