IDBDatabase.createObjectStore()
===============================

The `createObjectStore()` method of the [`IDBDatabase`](../idbdatabase) interface creates and returns a new object store or index.

The method takes the name of the store as well as a parameter object that lets you define important optional properties. You can use the property to uniquely identify individual objects in the store. As the property is an identifier, it should be unique to every object, and every object should have that property.

This method can be called *only* within a [`versionchange`](../idbtransaction#version_change) transaction.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    IDBDatabase.createObjectStore(name);
    IDBDatabase.createObjectStore(name, options);

### Parameters

`name`  
The name of the new object store to be created. Note that it is possible to create an object store with an empty name.

 `optionalParameters` <span class="badge inline optional">Optional</span>   
An options object whose attributes are optional parameters to the method. It includes the following properties:

<table><thead><tr class="header"><th>Attribute</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>keyPath</code></td><td>The <a href="../indexeddb_api/basic_concepts_behind_indexeddb#gloss_keypath">key path</a> to be used by the new object store. If empty or not specified, the object store is created without a key path and uses <a href="../indexeddb_api/basic_concepts_behind_indexeddb#gloss_outofline_key">out-of-line keys</a>. You can also pass in an array as a <code>keyPath</code>.</td></tr><tr class="even"><td><code>autoIncrement</code></td><td>If <code>true</code>, the object store has a <a href="../indexeddb_api/basic_concepts_behind_indexeddb#gloss_keygenerator">key generator</a>. Defaults to <code>false</code>.</td></tr></tbody></table>

Unknown parameters are ignored.

### Returns

A new [`IDBObjectStore`](../idbobjectstore).

### Exceptions

This method may raise a [`DOMException`](../domexception) with a [`DOMError`](../domerror) of one of the following types:

<table><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>InvalidStateError</code></td><td>Occurs if the method was not called from a <code>versionchange</code> transaction callback. For older WebKit browsers, you must call first.</td></tr><tr class="even"><td><code>TransactionInactiveError</code></td><td>Occurs if a request is made on a source database that doesn't exist (e.g. has been deleted or removed.) In Firefox previous to version 41, an <code>InvalidStateError</code> was raised in this case as well, which was misleading; this has now been fixed (see <a href="https://bugzilla.mozilla.org/show_bug.cgi?id=1176165">bug 1176165</a>.)</td></tr><tr class="odd"><td><code>ConstraintError</code></td><td>An object store with the given name (based on case-sensitive comparison) already exists in the connected database.</td></tr><tr class="even"><td><code>InvalidAccessError</code></td><td>If <code>autoIncrement</code> is set to true and <code>keyPath</code> is either an empty string or an array containing an empty string.</td></tr></tbody></table>

Example
-------

    // Let us open our database
    var request = window.indexedDB.open("toDoList", 4);

    // This handler is called when a new version of the database
    // is created, either when one has not been created before
    // or when a new version number is submitted by calling
    // window.indexedDB.open().
    // This handler is only supported in recent browsers.
    request.onupgradeneeded = function(event) {
      var db = event.target.result;

      db.onerror = function(event) {
        note.innerHTML += "<li>Error loading database.</li>";
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

      note.innerHTML += "<li>Object store created.</li>";
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbdatabase-createobjectstore">Indexed Database API 2.0<br />
<span class="small">The definition of 'createObjectStore()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbdatabase-createobjectstore">Indexed Database API 2.0<br />
<span class="small">The definition of 'createObjectStore()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`createObjectStore`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/createObjectStore" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/createObjectStore</a>
