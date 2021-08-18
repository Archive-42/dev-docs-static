IDBDatabase.objectStoreNames
============================

The `objectStoreNames` read-only property of the [`IDBDatabase`](../idbdatabase) interface is a [`DOMStringList`](../domstringlist) containing a list of the names of the [object stores](../indexeddb_api#gloss_object_store) currently in the connected database.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var list[] = IDBDatabase.objectStoreNames;

### Value

<span style="line-height: 1.5;">A [`DOMStringList`](../domstringlist) containing a list of the names of the </span>[object stores](../indexeddb_api#gloss_object_store)<span style="line-height: 1.5;"> currently in the connected database.</span>

<span style="line-height: 1.5;">Example</span>
----------------------------------------------

    // Let us open our database
    var DBOpenRequest = window.indexedDB.open("toDoList", 4);

    // these two event handlers act on the database being opened successfully, or not
    DBOpenRequest.onerror = function(event) {
      note.innerHTML += '<li>Error loading database.</li>';
    };

    DBOpenRequest.onsuccess = function(event) {
      note.innerHTML += '<li>Database initialised.</li>';

      // store the result of opening the database in the db variable. This is used a lot below
      db = DBOpenRequest.result;

      // This line will log the version of the connected database, which should be
      // an object that looks like { ['my-store-name'] }
      console.log(db.objectStoreNames);
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbdatabase-objectstorenames">Indexed Database API 2.0<br />
<span class="small">The definition of 'objectStoreNames' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbdatabase-objectstorenames">Indexed Database API 2.0<br />
<span class="small">The definition of 'objectStoreNames' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`objectStoreNames`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/objectStoreNames" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/objectStoreNames</a>
