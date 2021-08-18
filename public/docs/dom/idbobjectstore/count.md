IDBObjectStore.count()
======================

The `count()` method of the [`IDBObjectStore`](../idbobjectstore) interface returns an [`IDBRequest`](../idbrequest) object, and, in a separate thread, returns the total number of records that match the provided key or [`IDBKeyRange`](../idbkeyrange). If no arguments are provided, it returns the total number of records in the store.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var request = ObjectStore.count();
    var request = ObjectStore.count(query);

### Parameters

query <span class="badge inline optional">Optional</span>   
A key or [`IDBKeyRange`](../idbkeyrange) object that specifies a range of records you want to count.

### Return value

An [`IDBRequest`](../idbrequest) object on which subsequent events related to this operation are fired.

### Exceptions

This method may raise a [`DOMException`](../domexception) of one of the following types:

<table><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>InvalidStateError</code></td><td>This <a href="../idbobjectstore"><code>IDBObjectStore</code></a> has been deleted.</td></tr><tr class="even"><td><code>TransactionInactiveError</code></td><td>This <a href="../idbobjectstore"><code>IDBObjectStore</code></a>'s transaction is inactive.</td></tr><tr class="odd"><td><code>DataError</code></td><td>The specified key or key range is invalid.</td></tr></tbody></table>

Example
-------

In this simple fragment we create a transaction, retrieve an object store, then count the number of records in the store using `count()` — when the success handler fires, we log the count value (an integer) to the console.

    var transaction = db.transaction(['fThings'], 'readonly');
    var objectStore = transaction.objectStore('fThings');

    var countRequest = objectStore.count();
    countRequest.onsuccess = function() {
      console.log(countRequest.result);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbobjectstore-count">Indexed Database API 2.0<br />
<span class="small">The definition of 'count()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbobjectstore-count">Indexed Database API 2.0<br />
<span class="small">The definition of 'count()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`count`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/count" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/count</a>
