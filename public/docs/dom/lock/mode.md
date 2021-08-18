Locks.mode
==========

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `mode` read-only property of the [`Lock`](../lock) interface returns the access mode passed to [`LockManager.request()`](../lockmanager/request) when the lock was requested. The mode is either `"exclusive"` (the default) or `"shared"`.

Syntax
------

    var mode = Lock.mode

### Value

One of `"exclusive"` or `"shared"`.

Example
-------

The following examples show how the mode property is passed in the call to [`LockManager.request()`](../lockmanager/request). `LockManager` is the object returned by [`navigator.locks`](../navigator/locks).

    // Should show "exclusive" (the default)
    navigator.locks.request("my_resource", show_lock_properties);

    // Should show "exclusive"
    navigator.locks.request("my_resource", {mode: "exclusive"}, show_lock_properties);

    // Should show "shared"
    navigator.locks.request("my_resource", {mode: "shared"}, show_lock_properties);

    function show_lock_properties(lock) {
      console.log(`The lock name is: ${lock.name}`);
      console.log(`The lock mode is: ${lock.mode}`);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/web-locks/#dom-lock-mode">Web Locks API<br />
<span class="small">The definition of 'mode' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`mode`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Lock/mode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Lock/mode</a>
