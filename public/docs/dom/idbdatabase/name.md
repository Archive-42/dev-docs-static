IDBDatabase.name
================

The `name` read-only property of the `IDBDatabase` interface is a [`DOMString`](../domstring) that contains the name of the connected database.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var dbName = IDBDatabase.name;

### Value

A [`DOMString`](../domstring) containing the name of the connected database.

Example
-------

This example shows a database connection being opened, the resulting [`IDBDatabase`](../idbdatabase) object being stored in a db variable, and the name property then being logged. For a full example, see our [To-do Notifications](https://github.com/chrisdavidmills/to-do-notifications/tree/gh-pages)<span style="line-height: 1.5;"> app (</span>[view example live](https://chrisdavidmills.github.io/to-do-notifications/))<span style="line-height: 1.5;">.</span>

    // Let us open our database
    var DBOpenRequest = window.indexedDB.open("toDoList", 4);

    // these two event handlers act on the database being
    // opened successfully, or not
    DBOpenRequest.onerror = function(event) {
      note.innerHTML += '<li>Error loading database.</li>';
    };

    DBOpenRequest.onsuccess = function(event) {
      note.innerHTML += '<li>Database initialised.</li>';

      // store the result of opening the database in the db variable. This is used a lot below
      db = DBOpenRequest.result;

      // This line will log the name of the database, which should be "toDoList"
      console.log(db.name);
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbdatabase-name">Indexed Database API 2.0<br />
<span class="small">The definition of 'name' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbdatabase-name">Indexed Database API 2.0<br />
<span class="small">The definition of 'name' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`name`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/name" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/name</a>
