MutationObserver.disconnect()
=============================

The [`MutationObserver`](../mutationobserver) method `disconnect()` tells the observer to stop watching for mutations. The observer can be reused by calling its [`observe()`](observe) method again.

Syntax
------

    mutationObserver.disconnect()

### Parameters

None.

### Return value

`undefined`.

**Note:** All notifications of mutations that have already been *detected*, but *not yet reported* to the observer, are discarded.

Usage notes
-----------

If the element being observed is removed from the DOM, and then subsequently released by the browser's garbage collection mechanism, the `MutationObserver` is likewise deleted.

Example
-------

This example creates an observer, then disconnects from it, leaving it available for possible reuse.

    const targetNode = document.querySelector("#someElement");
    const observerOptions = {
      childList: true,
      attributes: true
    }

    const observer = new MutationObserver(callback);
    observer.observe(targetNode, observerOptions);

    /* some time later... */

    observer.disconnect();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-mutationobserver-disconnect">DOM<br />
<span class="small">The definition of 'MutationObserver.disconnect()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`disconnect`

18

12

14

11

15

6

≤37

18

14

14

6

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver/disconnect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver/disconnect</a>
