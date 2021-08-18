IDBObjectStore.openCursor()
===========================

The `openCursor()` method of the [`IDBObjectStore`](../idbobjectstore) interface returns an [`IDBRequest`](../idbrequest) object, and, in a separate thread, returns a new [`IDBCursorWithValue`](../idbcursorwithvalue) object. Used for iterating through an object store with a cursor.

To determine if the add operation has completed successfully, listen for the results’s `success` event.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var request = ObjectStore.openCursor();
    var request = ObjectStore.openCursor(query);
    var request = ObjectStore.openCursor(query, direction);

### Parameters

query <span class="badge inline optional">Optional</span>   
A key or [`IDBKeyRange`](../idbkeyrange) to be queried. If a single valid key is passed, this will default to a range containing only that key. If nothing is passed, this will default to a key range that selects all the records in this object store.

direction <span class="badge inline optional">Optional</span>   
An [`IDBCursorDirection`](https://w3c.github.io/IndexedDB/#enumdef-idbcursordirection) telling the cursor what direction to travel. Valid values are `"next"`, `"nextunique"`, `"prev"`, and `"prevunique"`. The default is `"next"`.

### Return value

An [`IDBRequest`](../idbrequest) object on which subsequent events related to this operation are fired.

### Exceptions

This method may raise a [`DOMException`](../domexception) of one of the following types:

<table><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>InvalidStateError</code></td><td>This <a href="../idbobjectstore"><code>IDBObjectStore</code></a> or <a href="../idbindex"><code>IDBIndex</code></a> has been deleted.</td></tr><tr class="even"><td><code>TransactionInactiveError</code></td><td>This <a href="../idbobjectstore"><code>IDBObjectStore</code></a>'s transaction is inactive.</td></tr><tr class="odd"><td><code>DataError</code></td><td>The specified key or key range is invalid.<br />
</td></tr></tbody></table>

Example
-------

In this simple fragment we create a transaction, retrieve an object store, then use a cursor to iterate through all the records in the object store:

    var transaction = db.transaction("name", "readonly");
    var objectStore = transaction.objectStore("name");
    var request = objectStore.openCursor();
    request.onsuccess = function(event) {
      var cursor = event.target.result;
      if(cursor) {
        // cursor.value contains the current record being iterated through
        // this is where you'd do something with the result
        cursor.continue();
      } else {
        // no more results
      }
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbindex-opencursor">Indexed Database API 2.0<br />
<span class="small">The definition of 'openCursor()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbobjectstore-opencursor">Indexed Database API 2.0<br />
<span class="small">The definition of 'openCursor()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`openCursor`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/openCursor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/openCursor</a>
