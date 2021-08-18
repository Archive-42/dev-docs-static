# IDBObjectStore.delete()

The `delete()` method of the [`IDBObjectStore`](../idbobjectstore) interface returns an [`IDBRequest`](../idbrequest) object, and, in a separate thread, deletes the specified record or records.

Either a key or an [`IDBKeyRange`](../idbkeyrange) can be passed, allowing one or multiple records to be deleted from a store. To delete all records in a store, use [`IDBObjectStore.clear`](clear).

Bear in mind that if you are using a [`IDBCursor`](../idbcursor), you can use the [`IDBCursor.delete()`](../idbcursor/delete) method to more efficiently delete the current record — without having to explicitly look up the record's key.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    var request = objectStore.delete(Key);

    var request = objectStore.delete(KeyRange);

### Parameters

Key  
The key of the record to be deleted, or an [`IDBKeyRange`](../idbkeyrange) to delete all records with keys in range.

### Return value

An [`IDBRequest`](../idbrequest) object on which subsequent events related to this operation are fired. The `request.result` attribute is set to undefined.

### <span style="line-height: 1.5;">Exceptions</span>

This method may raise a [`DOMException`](../domexception) of the following types:

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>TransactionInactiveError</code></td><td>This object store's transaction is inactive.</td></tr><tr class="even"><td><code>ReadOnlyError</code></td><td>The object store's transaction mode is read-only.</td></tr><tr class="odd"><td><code>InvalidStateError</code></td><td>The object store has been deleted.</td></tr><tr class="even"><td><code>DataError</code></td><td><p>The key is not a <a href="https://dvcs.w3.org/hg/IndexedDB/raw-file/tip/Overview.html#dfn-valid-key">valid key</a> or a <a href="https://dvcs.w3.org/hg/IndexedDB/raw-file/tip/Overview.html#dfn-key-range">key range</a>.</p></td></tr></tbody></table>

## Example

In the following code snippet, we open a read/write transaction on our database and delete one specific record out of our object store using `delete()` — a sample record with the key "Walk dog". For a full working example, see our [To-do Notifications](https://github.com/mdn/to-do-notifications/)<span style="line-height: 1.5;"> app (</span>[view example live](https://mdn.github.io/to-do-notifications/)<span style="line-height: 1.5;">.)</span>

    // Let us open our database
    var DBOpenRequest = window.indexedDB.open("toDoList", 4);

    DBOpenRequest.onsuccess = function(event) {
      note.innerHTML += '<li>Database initialised.</li>';

      // store the result of opening the database in the db variable. This is used a lot below
      db = DBOpenRequest.result;

      // Run the deleteData() function to delete a record from the database
      deleteData();
    };

    function deleteData() {
      // open a read/write db transaction, ready for deleting the data
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

      // Make a request to delete the specified record out of the object store
      var objectStoreRequest = objectStore.delete("Walk dog");

      objectStoreRequest.onsuccess = function(event) {
        // report the success of our request
        note.innerHTML += '<li>Request successful.</li>';
      };
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbobjectstore-delete">Indexed Database API 2.0<br />
<span class="small">The definition of 'delete()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbobjectstore-delete">Indexed Database API 2.0<br />
<span class="small">The definition of 'delete()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

## Browser compatibility

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

`delete`

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

## See also

- [Using IndexedDB](../indexeddb_api/using_indexeddb)
- Starting transactions: [`IDBDatabase`](../idbdatabase)
- Using transactions: [`IDBTransaction`](../idbtransaction)
- Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
- Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
- Using cursors: [`IDBCursor`](../idbcursor)
- Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/delete" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/delete</a>
