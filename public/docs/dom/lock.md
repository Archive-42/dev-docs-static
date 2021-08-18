# Lock

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Lock` interface of the [Web Locks API](web_locks_api) provides the name and mode of a previously requested lock, which is received in the callback to [`LockManager.request()`](lockmanager/request).

## Properties

[`Lock.mode`](lock/mode) <span class="badge inline readonly">Read only </span>  
Returns the access mode passed to [`LockManager.request()`](lockmanager/request) when the lock was requested. The mode is either `"exclusive"` (the default) or `"shared"`.

[`Lock.name`](lock/name) <span class="badge inline readonly">Read only </span>  
Returns the name passed to [`LockManager.request()`](lockmanager/request) when the lock was requested.

## Examples

The following examples show how the mode and name properties are passed in the call to [`LockManager.request()`](lockmanager/request). `LockManager` is the object returned by [`navigator.locks`](navigator/locks).

    navigator.locks.request("net_db_sync", show_lock_properties);
    navigator.locks.request("another_lock", {mode: "shared"}, show_lock_properties);

    function show_lock_properties(lock) {
      console.log(`The lock name is: ${lock.name}`);
      console.log(`The lock mode is: ${lock.mode}`);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/web-locks/#api-lock">Web Locks API<br />
<span class="small">The definition of 'Lock' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`Lock`

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

`name`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Lock" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Lock</a>
