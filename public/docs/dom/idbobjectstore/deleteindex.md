IDBObjectStore.deleteIndex()
============================

The `deleteIndex()` method of the [`IDBObjectStore`](../idbobjectstore) interface destroys the index with the specified name in the connected database, used during a version upgrade.

Note that this method must be called only from a `VersionChange` transaction mode callback. Note that this method synchronously modifies the [`IDBObjectStore.indexNames`](indexnames) property.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    objectStore.deleteIndex(indexName);

### Parameters

indexName  
The name of the existing index to remove.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

### Exceptions

This method may raise a [`DOMException`](../domexception) of one of the following types:

<table><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>InvalidStateError</code></td><td>Occurs if the method was not called from a <code>versionchange</code> transaction mode callback.</td></tr><tr class="even"><td><code>TransactionInactiveError</code></td><td>Occurs if the transaction this <a href="../idbobjectstore"><code>IDBObjectStore</code></a> belongs to is not active (e.g. has been deleted or removed.) In Firefox previous to version 41, an <code>InvalidStateError</code> was raised in this case as well, which was misleading; this has now been fixed (see <a href="https://bugzilla.mozilla.org/show_bug.cgi?id=1176165">bug 1176165</a>.)</td></tr><tr class="odd"><td><code>NotFoundError</code></td><td>Occurs if there is no index with the given name (case-sensitive) in the database.<br />
</td></tr></tbody></table>

Example
-------

In the following example you can see the [`IDBOpenDBRequest.onupgradeneeded`](../idbopendbrequest/onupgradeneeded) handler being used to update the database structure if a database with a higher version number is loaded. [`IDBObjectStore.createIndex`](createindex) is used to create new indexes on the object store, after which we delete the unneeded old indexes with `deleteIndex()`. For a full working example, see our [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) app ([view example live](https://mdn.github.io/to-do-notifications/).)

    var db;

    // Let us open our database
    var DBOpenRequest = window.indexedDB.open("toDoList", 4);

    // these two event handlers act on the database being opened successfully, or not
    DBOpenRequest.onerror = function(event) {
      note.innerHTML += '<li>Error loading database.</li>';
    };

    DBOpenRequest.onsuccess = function(event) {
      note.innerHTML += '<li>Database initialised.</li>';

      // store the result of opening the database in the db variable. This is used a lot below
      db = this.result;

      // Run the displayData() function to populate the task list with all the to-do list data already in the IDB
      displayData();
    };

    // This event handles the event whereby a new version of the database needs to be created
    // Either one has not been created before, or a new version number has been submitted via the
    // window.indexedDB.open line above
    //it is only implemented in recent browsers
    DBOpenRequest.onupgradeneeded = function(event) {
      var db = this.result;

      db.onerror = function(event) {
        note.innerHTML += '<li>Error loading database.</li>';
      };

      // Create an objectStore for this database
      var objectStore = db.createObjectStore("toDoList", { keyPath: "taskTitle" });

      // define what data items the objectStore will contain

      objectStore.createIndex("hours", "hours", { unique: false });
      objectStore.createIndex("minutes", "minutes", { unique: false });
      objectStore.createIndex("day", "day", { unique: false });
      objectStore.createIndex("month", "month", { unique: false });
      objectStore.createIndex("year", "year", { unique: false });
      objectStore.createIndex("notified", "notified", { unique: false });

      objectStore.deleteIndex("seconds");
      objectStore.deleteIndex("contact");

    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbobjectstore-deleteindex">Indexed Database API 2.0<br />
<span class="small">The definition of 'deleteIndex()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbobjectstore-deleteindex">Indexed Database API 2.0<br />
<span class="small">The definition of 'deleteIndex()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`deleteIndex`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/deleteIndex" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/deleteIndex</a>
