# LockManager

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `LockManager` interface of the [Web Locks API](web_locks_api) provides methods for requesting a new [`Lock`](lock) object and querying for an existing `Lock` object. To get an instance of `LockManager`, call [`navigator.locks`](navigator/locks).

## Methods

[`LockManager.request()`](lockmanager/request)  
Requests a [`Lock`](lock) object with parameters specifying its name and characteristics.

[`LockManager.query()`](lockmanager/query)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a <span class="page-not-created">`LockManagerSnapshot`</span> which contains information about held and pending locks.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/web-locks/#api-lock-manager">Web Locks API<br />
<span class="small">The definition of 'LockManager' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`LockManager`

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

`request`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/LockManager" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/LockManager</a>
