IDBObjectStore.createIndex()
============================

The `createIndex()` method of the [`IDBObjectStore`](../idbobjectstore) interface creates and returns a new [`IDBIndex`](../idbindex) object in the connected database. It creates a new field/column defining a new data point for each database record to contain.

Bear in mind that IndexedDB indexes can contain *any* JavaScript data type; IndexedDB uses the [structured clone algorithm](../web_workers_api/structured_clone_algorithm) to serialize stored objects, which allows for storage of simple and complex objects.

Note that this method must be called only from a `VersionChange` transaction mode callback.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var myIDBIndex = objectStore.createIndex(indexName, keyPath);
    var myIDBIndex = objectStore.createIndex(indexName, keyPath, objectParameters);

### Parameters

indexName  
The name of the index to create. Note that it is possible to create an index with an empty name.

keyPath  
The key path for the index to use. Note that it is possible to create an index with an empty `keyPath`, and also to pass in a sequence (array) as a `keyPath`.

objectParameters <span class="badge inline optional">Optional</span>   
An <span class="page-not-created">`IDBIndexParameters`</span> object, which can include the following properties:

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Attribute</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>unique</code></td><td>If true, the index will not allow duplicate values for a single key.</td></tr><tr class="even"><td><code>multiEntry</code></td><td>If <code>true</code>, the index will add an entry in the index for each array element when the <em>keyPath</em> resolves to an Array. If <code>false</code>, it will add one single entry containing the Array.</td></tr><tr class="odd"><td><code>locale</code></td><td><p>Currently Firefox-only (43+), this allows you to specify a locale for the index. Any sorting operations performed on the data via key ranges will then obey sorting rules of that locale (see <a href="../indexeddb_api/using_indexeddb#locale-aware_sorting">locale-aware sorting</a>.) You can specify its value in one of three ways:</p><ul><li><code>string</code>: A string containing a specific locale code, e.g. <code>en-US</code>, or <code>pl</code>.</li><li><code>auto</code>: The platform default locale will be used (may be changed by user agent settings.)</li><li><code>null or undefined</code>: If no locale is specified, normal JavaScript sorting will be used — not locale-aware.</li></ul></td></tr></tbody></table>

### Return value

<span style="line-height: 1.5;">An [`IDBIndex`](../idbindex) object: the newly created index.</span>

### <span style="line-height: 1.5;">Exceptions</span>

<span style="line-height: 1.5;">This method may raise a [`DOMException`](../domexception) of one of the following types:</span>

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>ConstraintError</code></td><td>Occurs if an index with the same name already exists in the database. Index names are case-sensitive.</td></tr><tr class="even"><td><code>InvalidAccessError</code></td><td>Occurs if the provided key path is a sequence, and <code>multiEntry</code> is set to <code>true</code> in the <code>objectParameters</code> object.</td></tr><tr class="odd"><td><code>InvalidStateError</code></td><td><p>Occurs if either:</p><ul><li>The method was not called from a <code>versionchange</code> transaction mode callback, i.e. from inside a <a href="../idbopendbrequest/onupgradeneeded"><code>IDBOpenDBRequest.onupgradeneeded</code></a> handler.</li><li>The object store has been deleted.</li></ul></td></tr><tr class="even"><td><code>SyntaxError</code></td><td>Occurs if the provided <code>keyPath</code> is not a <a href="https://www.w3.org/TR/IndexedDB/#dfn-valid-key-path">valid key path</a>.</td></tr><tr class="odd"><td><code>TransactionInactiveError</code></td><td>Occurs if the transaction this <a href="../idbobjectstore"><code>IDBObjectStore</code></a> belongs to is not active (e.g. has been deleted or removed.) In Firefox previous to version 41, an <code>InvalidStateError</code> was raised in this case as well, which was misleading; this has now been fixed (see <a href="https://bugzilla.mozilla.org/show_bug.cgi?id=1176165">bug 1176165</a>.)</td></tr></tbody></table>

Example
-------

In the following example you can see the [`IDBOpenDBRequest.onupgradeneeded`](../idbopendbrequest/onupgradeneeded) handler being used to update the database structure if a database with a higher version number is loaded. `createIndex()` is used to create new indexes on the object store. For a full working example, see our [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) app ([view example live](https://mdn.github.io/to-do-notifications/).)

    var db;

    // Let us open our database
    var DBOpenRequest = window.indexedDB.open("toDoList", 4);

    // Two event handlers for opening the database.
    DBOpenRequest.onerror = function(event) {
      note.innerHTML += '<li>Error loading database.</li>';
    };

    DBOpenRequest.onsuccess = function(event) {
      note.innerHTML += '<li>Database initialised.</li>';

      // store the result of opening the database in the db variable.
      // This is used a lot below.
      db = request.result;

      // Run the displayData() function to populate the task list with
      // all the to-do list data already in the IDB
      displayData();
    };

    // This handler fires when a new database is created and indicates
    // either that one has not been created before, or a new version
    // was submitted with window.indexedDB.open(). (See above.)
    // It is only implemented in recent browsers.
    DBOpenRequest.onupgradeneeded = function(event) {
      var db = event.target.result;

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
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbobjectstore-createindex">Indexed Database API 2.0<br />
<span class="small">The definition of 'createIndex()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbobjectstore-createindex">Indexed Database API 2.0<br />
<span class="small">The definition of 'createIndex()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`createIndex`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/createIndex" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/createIndex</a>
