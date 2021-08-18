IDBDatabase.version
===================

The `version` property of the [`IDBDatabase`](../idbdatabase) interface is a [64-bit integer](https://developer.mozilla.org/en-US/docs/NSPR_API_Reference/Long_Long_%2864-bit%29_Integers) that contains the version of the connected database. When a database is first created, this attribute is an empty string.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var myInteger = IDBDatabase.version;

### Value

An integer containing the version of the connected database.

Example
-------

    // Let us open our database
    var DBOpenRequest = window.indexedDB.open("toDoList", 4);

    // these two event handlers act on the database
    // being opened successfully, or not
    DBOpenRequest.onerror = function(event) {
      note.innerHTML += '<li>Error loading database.</li>';
    };

    DBOpenRequest.onsuccess = function(event) {
      note.innerHTML += '<li>Database initialised.</li>';

      // store the result of opening the database in the db variable. This is used a lot below
      db = DBOpenRequest.result;

      // This line will log the version of the connected database, which should be "4"
      console.log(db.version);
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbdatabase-version">Indexed Database API 2.0<br />
<span class="small">The definition of 'version' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbdatabase-version">Indexed Database API 2.0<br />
<span class="small">The definition of 'version' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/version" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/version</a>
