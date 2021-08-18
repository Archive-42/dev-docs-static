IDBVersionChangeEvent.oldVersion
================================

The `oldVersion` read-only property of the [`IDBVersionChangeEvent`](../idbversionchangeevent) interface returns the old version number of the database.

When the opened database doesn't exist yet, the value of `oldVersion` is 0.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var oldVersion = IDBVersionChangeEvent.oldVersion

### Value

A [64-bit integer](https://developer.mozilla.org/en-US/docs/NSPR_API_Reference/Long_Long_(64-bit)_Integers).

Example
-------

    var dbName = "sampleDB";
    var dbVersion = 2;
    var request = indexedDB.open(dbName, dbVersion);

    request.onupgradeneeded = function(e) {
      var db = request.result;
      if (e.oldVersion < 1) {
        db.createObjectStore("store1");
      }

      if (e.oldVersion < 2) {
        db.deleteObjectStore("store1");
        db.createObjectStore("store2");
      }

      // etc. for version < 3, 4...
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbversionchangeevent-oldversion">Indexed Database API 2.0<br />
<span class="small">The definition of 'oldVersion' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbversionchangeevent-oldversion">Indexed Database API 2.0<br />
<span class="small">The definition of 'oldVersion' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`oldVersion`

23

12

10

10

15

7

≤37

25

22

14

8

1.5

See also
--------

-   [Using IndexedDB](../indexeddb_api/using_indexeddb)
-   Starting transactions: [`IDBDatabase`](../idbdatabase)
-   Using transactions: [`IDBTransaction`](../idbtransaction)
-   Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
-   Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
-   Using cursors: [`IDBCursor`](../idbcursor)
-   Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBVersionChangeEvent/oldVersion" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBVersionChangeEvent/oldVersion</a>
