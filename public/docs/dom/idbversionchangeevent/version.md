IDBVersionChangeEvent.version
=============================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Warning**

While this property is still implemented in older browsers, the latest specification replaces it with the `oldVersion` and `newVersion` attributes. See the compatibility table to know what browsers support them.

The `version` property of the [`IDBVersionChangeEvent`](../idbversionchangeevent) interface returns The new version of the database in a [versionchange](../idbtransaction#version_change) transaction.

Syntax
------

    readonly    attribute unsigned long long? version;

Value
-----

A [64-bit integer](https://developer.mozilla.org/en-US/docs/NSPR_API_Reference/Long_Long_(64-bit)_Integers).

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

`version`

12

≤18

10

No

No

No

≤37

18

22

22

No

1.0

See also
--------

-   [Using IndexedDB](../indexeddb_api/using_indexeddb)
-   Starting transactions: [`IDBDatabase`](../idbdatabase)
-   Using transactions: [`IDBTransaction`](../idbtransaction)
-   Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
-   Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
-   Using cursors: [`IDBCursor`](../idbcursor)
-   Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBVersionChangeEvent/version" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBVersionChangeEvent/version</a>
