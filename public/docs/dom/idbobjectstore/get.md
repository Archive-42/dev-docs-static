IDBObjectStore.get()
====================

The `get()` method of the [`IDBObjectStore`](../idbobjectstore) interface returns an [`IDBRequest`](../idbrequest) object, and, in a separate thread, returns the object store selected by the specified key. This is for retrieving specific records from an object store.

If a value is successfully found, then a structured clone of it is created and set as the `result` of the request object.

**Note**

This method produces the same result for: a) a record that doesn't exist in the database and b) a record that has an undefined value. To tell these situations apart, call the `openCursor()` method with the same key. That method provides a cursor if the record exists, and no cursor if it does not.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var request = objectStore.get(key);

### Parameters

key  
The key or key range that identifies the record to be retrieved.

### Return value

An [`IDBRequest`](../idbrequest) object on which subsequent events related to this operation are fired.

### <span style="line-height: 1.5;">Exceptions</span>

<span style="line-height: 1.5;">This method may raise a [`DOMException`](../domexception) of one of the following types:</span>

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>TransactionInactiveError</code></td><td>This <a href="../idbobjectstore"><code>IDBObjectStore</code></a>'s transaction is inactive.</td></tr><tr class="even"><td><code>DataError</code></td><td><p>The key or key range provided contains an invalid key.</p></td></tr><tr class="odd"><td><code>InvalidStateError</code></td><td>The <a href="../idbobjectstore"><code>IDBObjectStore</code></a> has been deleted or removed.<br />
</td></tr></tbody></table>

Example
-------

In the following code snippet, we open a read/write transaction on our database and get one specific record from object store using `get()` — a sample record with the key "Walk dog". Once this data object is retrieved, you could then update it using normal JavaScript, then put it back into the database using a [`IDBObjectStore.put`](put) operation. For a full working example, see our [To-do Notifications](https://github.com/mdn/to-do-notifications/)<span style="line-height: 1.5;"> app (</span>[view example live](https://mdn.github.io/to-do-notifications/)<span style="line-height: 1.5;">.)</span>

    // Let us open our database
    var DBOpenRequest = window.indexedDB.open("toDoList", 4);

    DBOpenRequest.onsuccess = function(event) {
      note.innerHTML += '<li>Database initialised.</li>';

      // store the result of opening the database in the db variable.
      // This is used a lot below
      db = DBOpenRequest.result;

      // Run the getData() function to get the data from the database
      getData();
    };

    function getData() {
      // open a read/write db transaction, ready for retrieving the data
      var transaction = db.transaction(["toDoList"], "readwrite");

      // report on the success of the transaction completing, when everything is done
      transaction.oncomplete = function(event) {
        note.innerHTML += '<li>Transaction completed.</li>';
      };

      transaction.onerror = function(event) {
        note.innerHTML += '<li>Transaction not opened due to error: ' + transaction.error + '</li>';
      };

      // create an object store on the transaction
      var objectStore = transaction.objectStore("toDoList");

      // Make a request to get a record by key from the object store
      var objectStoreRequest = objectStore.get("Walk dog");

      objectStoreRequest.onsuccess = function(event) {
        // report the success of our request
        note.innerHTML += '<li>Request successful.</li>';

        var myRecord = objectStoreRequest.result;
      };

    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbobjectstore-get">Indexed Database API 2.0<br />
<span class="small">The definition of 'get()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbobjectstore-get">Indexed Database API 2.0<br />
<span class="small">The definition of 'get()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`get`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/get" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/get</a>
