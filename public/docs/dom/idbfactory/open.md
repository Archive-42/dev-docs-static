IDBFactory.open()
=================

The `open()` method of the [`IDBFactory`](../idbfactory) interface requests opening a [connection to a database](../indexeddb_api#gloss_database_connection).

The method returns an [`IDBOpenDBRequest`](../idbopendbrequest) object immediately, and performs the open operation asynchronously. If the operation is successful, a `success` event is fired on the request object that is returned from this method, with its `result` attribute set to the new [`IDBDatabase`](../idbdatabase) object for the connection.

May trigger `upgradeneeded`, `blocked` or `versionchange` events.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

For the current standard:

    var IDBOpenDBRequest = indexedDB.open(name);
    var IDBOpenDBRequest = indexedDB.open(name, version);

### Parameters

name  
The name of the database.

version <span class="badge inline optional">Optional</span>   
Optional. The version to open the database with. If the version is not provided and the database exists, then a connection to the database will be opened without changing its version. If the version is not provided and the database does not exist, then it will be created with version `1`.

#### Experimental Gecko options object

options (version and storage) <span class="badge inline optional">Optional</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
In Gecko, since [version 26](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Releases/26), you can include a non-standard `options` object as a parameter of [`IDBFactory.open`](open) that contains the `version` number of the database, plus a storage value that specifies whether you want to use `persistent` or `temporary` storage.

**Warning:** The `storage` attribute is deprecated and will soon be removed from Gecko. You should use [`StorageManager.persist()`](../storagemanager/persist) to get persistent storage instead.

**Note**: You can find out more information on the different available storage types, and how Firefox handles client-side data storage, at [Browser storage limits and eviction criteria](../indexeddb_api/browser_storage_limits_and_eviction_criteria).

### Return value

A [`IDBOpenDBRequest`](../idbopendbrequest) object on which subsequent events related to this request are fired.

### Exceptions

This method may raise a [`DOMException`](../domexception) of the following types:

<table><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>TypeError</code></td><td>The value of version is zero or a negative number or not a number.</td></tr></tbody></table>

Example
-------

Example of calling `open` with the current specification's `version` parameter:

    var request = window.indexedDB.open("toDoList", 4);

In the following code snippet, we make a request to open a database, and include handlers for the success and error cases. For a full working example, see our [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) app ([view example live](https://mdn.github.io/to-do-notifications/).)

    var note = document.querySelector("ul");

    // In the following line, you should include the prefixes
    // of implementations you want to test.
    window.indexedDB = window.indexedDB || window.mozIndexedDB || window.webkitIndexedDB || window.msIndexedDB;
    // DON'T use "var indexedDB = ..." if you're not in a function.
    // Moreover, you may need references to some window.IDB* objects:
    window.IDBTransaction = window.IDBTransaction || window.webkitIDBTransaction || window.msIDBTransaction;
    window.IDBKeyRange = window.IDBKeyRange || window.webkitIDBKeyRange || window.msIDBKeyRange;
    // (Mozilla has never prefixed these objects, so we don't
    //  need window.mozIDB*)

    // Let us open version 4 of our database
    var DBOpenRequest = window.indexedDB.open("toDoList", 4);

    // these two event handlers act on the database being opened
    // successfully, or not
    DBOpenRequest.onerror = function(event) {
      note.innerHTML += '<li>Error loading database.</li>';
    };

    DBOpenRequest.onsuccess = function(event) {
      note.innerHTML += '<li>Database initialised.</li>';

      // store the result of opening the database in the db
      // variable. This is used a lot later on, for opening
      // transactions and suchlike.
      db = DBOpenRequest.result;
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbfactory-open">Indexed Database API 2.0<br />
<span class="small">The definition of 'open()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbfactory-open">Indexed Database API 2.0<br />
<span class="small">The definition of 'open()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

See also
--------

-   [Using IndexedDB](../indexeddb_api/using_indexeddb)
-   Starting transactions: [`IDBDatabase`](../idbdatabase)
-   Using transactions: [`IDBTransaction`](../idbtransaction)
-   Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
-   Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
-   Using cursors: [`IDBCursor`](../idbcursor)
-   Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBFactory/open" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBFactory/open</a>
