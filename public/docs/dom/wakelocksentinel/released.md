WakeLockSentinel.released
=========================

**Draft**

This page is not complete.

The read-only `released` property of the [`WakeLockSentinel`](../wakelocksentinel) interface returns a boolean that indicates whether a [`WakeLockSentinel`](../wakelocksentinel) has been released yet.

Syntax
------

    var released = sentinel.released;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). Its value is `false` until the [`WakeLockSentinel`](../wakelocksentinel) has been released (either through a call to [`WakeLockSentinel.release()`](release) or because the lock has been released automatically) and the [`WakeLockSentinel.onrelease`](onrelease) event has been emitted, after which it becomes `true` and no longer changes.

Examples
--------

This example shows how `released`'s value changes within a [`WakeLockSentinel`](../wakelocksentinel)'s life cycle.

    const sentinel = await navigator.wakeLock.request('screen');
    console.log(sentinel.released);  // Logs "false"

    sentinel.onrelease = () => {
      console.log(sentinel.released);  // Logs "true"
    };

    await sentinel.release();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/screen-wake-lock/#dom-wakelocksentinel-released">Screen Wake Lock API<br />
<span class="small">The definition of 'released' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`released`

87

87

No

No

Yes

No

87

87

No

Yes

No

14.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WakeLockSentinel/released" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WakeLockSentinel/released</a>
