UserDataHandler
===============

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Note:**This method was removed from Firefox 26 and onward.

Summary
-------

When associating user data with a key on a node, `Node.setUserData()` can also accept, in its third argument, a handler which will be called when the object is cloned, imported, deleted, renamed, or adopted. Per the specification, exceptions should not be thrown in a `UserDataHandler`. In both `document.importNode()` and `Node.cloneNode()`, although user data is not copied over, the handler will be called.

Properties
----------

None.

Methods
-------

`handle (operation, key, data, src, dst)` (no return value)

This method is a callback which will be called if a node is being cloned, imported, renamed and as well, if deleted or adopted.

-   `operation` (unsigned short) is an operation type integer (see below).
-   `key` ([`DOMString`](domstring)) is the user key.
-   `data` ([`DOMUserData`](domuserdata)) is the user data.
-   `src` ([`Node`](node)) is the source node (`null` if being deleted).
-   `dst` ([`Node`](node)) is the destination node (if any, or `null`).

Constants
---------

<table><thead><tr class="header"><th>Constant</th><th>Value</th><th>Operation</th></tr></thead><tbody><tr class="odd"><td><code>NODE_CLONED</code></td><td>1</td><td><code>Node.cloneNode()</code></td></tr><tr class="even"><td><code>NODE_IMPORTED</code></td><td>2</td><td><code>Document.importNode()</code></td></tr><tr class="odd"><td><code>NODE_DELETED</code> <span class="notecard inline warning">Unimplemented (see <a href="https://bugzilla.mozilla.org/show_bug.cgi?id=550400">bug 550400</a>)</span></td><td>3</td><td></td></tr><tr class="even"><td><code>NODE_RENAMED</code> <span class="notecard inline warning">Unimplemented</span></td><td>4</td><td><code>Node.renameNode()</code></td></tr><tr class="odd"><td><code>NODE_ADOPTED</code></td><td>5</td><td><code>Document.adoptNode()</code></td></tr></tbody></table>

(`NODE_RENAMED` is currently not supported since `Node.renameNode()` is not supported.)

Specifications
--------------

[DOM Level 3 Core: UserDataHandler](https://www.w3.org/TR/DOM-Level-3-Core/core.html#UserDataHandler)

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

`UserDataHandler`

No

No

4-22

No

No

No

No

No

4-22

No

No

No

`handle`

No

No

4-22

No

No

No

No

No

4-22

No

No

No

See also
--------

-   [`DOMUserData`](domuserdata)
-   [`Node.getUserData`](node/getuserdata), [`Node.setUserData`](node/setuserdata)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/UserDataHandler" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/UserDataHandler</a>
