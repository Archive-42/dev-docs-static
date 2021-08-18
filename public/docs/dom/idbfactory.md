IDBFactory
==========

The `IDBFactory` interface of the [IndexedDB API](indexeddb_api) lets applications asynchronously access the indexed databases. The object that implements the interface is `window.indexedDB`. You open — that is, create and access — and delete a database with this object, and not directly with `IDBFactory`.

**Note:** This feature is available in [Web Workers](web_workers_api).

Methods
-------

[`IDBFactory.open`](idbfactory/open)  
The current method to request opening a [connection to a database](indexeddb_api#gloss_database_connection).

[`IDBFactory.deleteDatabase`](idbfactory/deletedatabase)  
A method to request the deletion of a database.

[`IDBFactory.cmp`](idbfactory/cmp)  
A method that compares two keys and returns a result indicating which one is greater in value.

[`IDBFactory.databases`](idbfactory/databases)  
A method that returns a list of all available databases, including their names and versions.

Example
-------

In the following code snippet, we make a request to open a database, and include handlers for the success and error cases. For a full working example, see our [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) app ([view example live](https://mdn.github.io/to-do-notifications/).)

    // In the following line, you should include the prefixes of implementations you want to test.
    window.indexedDB = window.indexedDB || window.mozIndexedDB || window.webkitIndexedDB || window.msIndexedDB;
    // DON'T use "var indexedDB = ..." if you're not in a function.
    // Moreover, you may need references to some window.IDB* objects:
    window.IDBTransaction = window.IDBTransaction || window.webkitIDBTransaction || window.msIDBTransaction;
    window.IDBKeyRange = window.IDBKeyRange || window.webkitIDBKeyRange || window.msIDBKeyRange;
    // (Mozilla has never prefixed these objects, so we don't need window.mozIDB*)

    // Let us open version 4 of our database
    var DBOpenRequest = window.indexedDB.open("toDoList", 4);

    // these two event handlers act on the database being opened successfully, or not
    DBOpenRequest.onerror = function(event) {
      console.error("Error loading database.");
    };

    DBOpenRequest.onsuccess = function(event) {
      console.info("Database initialised.");

      // store the result of opening the database in the db variable. This is used a lot later on, for opening transactions and suchlike.
      db = DBOpenRequest.result;
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#factory-interface">Indexed Database API 2.0<br />
<span class="small">The definition of 'IDBFactory' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`IDBFactory`

24

23-57

12

16

10-16

10

15

7

≤37

≤37-57

25

25-57

22

14

8

1.5

1.5-7.0

`cmp`

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

`databases`

71

79

No

See [bug 934640](https://bugzil.la/934640).

No

58

14

71

71

No

See [bug 934640](https://bugzil.la/934640).

Yes

14

10.0

`deleteDatabase`

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

`open`

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

`worker_support`

Yes

≤18

37

?

Yes

?

Yes

Yes

37

Yes

?

Yes

See also
--------

-   [Using IndexedDB](indexeddb_api/using_indexeddb)
-   Starting transactions: [`IDBDatabase`](idbdatabase)
-   Using transactions: [`IDBTransaction`](idbtransaction)
-   Setting a range of keys: [`IDBKeyRange`](idbkeyrange)
-   Retrieving and making changes to your data: [`IDBObjectStore`](idbobjectstore)
-   Using cursors: [`IDBCursor`](idbcursor)
-   Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBFactory" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBFactory</a>
