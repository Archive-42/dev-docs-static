# Locks.name

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `name` read-only property of the [`Lock`](../lock) interface returns the _name_ passed to [`LockManager.request`](../lockmanager/request) selected when the lock was requested.

The name of a lock is passed by script when the lock is requested. The name is selected by the developer to represent an abstract resource for which use is being coordinated across multiple tabs, workers, or other code within the origin. For example, if only one tab of a web application should be synchronizing network resources with an offline database, it could use a lock name such as `"net_db_sync"`.

## Syntax

    var name = Lock.name

### Value

A [`DOMString`](../domstring).

## Example

The following examples show how the name property passed in the call to [`LockManager.request()`](../lockmanager/request). `LockManager` is the object returned by [`navigator.locks`](../navigator/locks).

    navigator.locks.request("net_db_sync", show_lock_properties);

    function show_lock_properties(lock) {
      console.log(`The lock name is: ${lock.name}`);
      console.log(`The lock mode is: ${lock.mode}`);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/web-locks/#dom-lock-name">Web Locks API<br />
<span class="small">The definition of 'name' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Lock/name" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Lock/name</a>
