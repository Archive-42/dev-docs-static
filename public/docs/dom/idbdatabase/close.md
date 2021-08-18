IDBDatabase.close()
===================

The `close()` method of the [`IDBDatabase`](../idbdatabase) interface returns immediately and closes the connection in a separate thread.

The connection is not actually closed until all transactions created using this connection are complete. No new transactions can be created for this connection once this method is called. Methods that create transactions throw an exception if a closing operation is pending.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    IDBDatabase.close();

Example
-------

    // Let us open our database
    var DBOpenRequest = window.indexedDB.open("toDoList", 4); // opening a database.

    // Create event handlers for both success and failure of
    DBOpenRequest.onerror = function(event) {
      note.innerHTML += "<li>Error loading database.</li>";
    };

    DBOpenRequest.onsuccess = function(event) {
      note.innerHTML += "<li>Database initialised.</li>";

      // store the result of opening the database in the db variable.
      db = DBOpenRequest.result;

      // now let"s close the database again!
      db.close();
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbdatabase-close">Indexed Database API 2.0<br />
<span class="small">The definition of 'close()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbdatabase-close">Indexed Database API 2.0<br />
<span class="small">The definition of 'close()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`close`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/close" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/close</a>
