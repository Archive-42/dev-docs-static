# IDBTransaction.commit()

The `commit()` method of the [`IDBTransaction`](../idbtransaction) interface commits the transaction if it is called on an active transaction.

Note that `commit()` doesn't normally _have_ to be called — a transaction will automatically commit when all outstanding requests have been satisfied and no new requests have been made. `commit()` can be used to start the commit process without waiting for events from outstanding requests to be dispatched.

If it is called on a transaction that is not active, it throws an [`InvalidStateError`](../domexception#exception-invalidstateerror) `DOMException`.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    transaction.commit();

### Parameters

None.

### Return value

Void.

### Exceptions

<table><thead><tr class="header"><th><strong>Exception</strong></th><th><strong>Description</strong></th></tr></thead><tbody><tr class="odd"><td><a href="../domexception#exception-invalidstateerror"><code>InvalidStateError</code></a></td><td>The transaction state is not active.</td></tr></tbody></table>

## Examples

    // open a read/write db transaction, ready for adding the data
    var transaction = db.transaction(["myDB"], "readwrite");

    // report on the success of opening the transaction
    transaction.oncomplete = function(event) {
      note.innerHTML += '<li>Transaction completed: database modification finished.</li>';
    };

    transaction.onerror = function(event) {
      note.innerHTML += '<li>Transaction not opened due to error. Duplicate items not allowed.</li>';
    };

    // create an object store on the transaction
    var objectStore = transaction.objectStore("myObjStore");

    // add our newItem object to the object store
    var objectStoreRequest = objectStore.add(newItem[0]);

    objectStoreRequest.onsuccess = function(event) {
      // report the success of the request (this does not mean the item
      // has been stored successfully in the DB - for that you need transaction.onsuccess)
      note.innerHTML += '<li>Request successful.</li>';
    };

    // Force the changes to be committed to the database asap
    transaction.commit();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbtransaction-commit">Indexed Database API 2.0<br />
<span class="small">The definition of 'IDBTransaction.commit()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`commit`

76

79

74

No

63

No

76

76

No

54

No

12.0

## See also

- [Using IndexedDB](../indexeddb_api/using_indexeddb)
- Starting transactions: [`IDBDatabase`](../idbdatabase)
- Using transactions: [`IDBTransaction`](../idbtransaction)
- Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
- Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
- Using cursors: [`IDBCursor`](../idbcursor)
- Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBTransaction/commit" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBTransaction/commit</a>
