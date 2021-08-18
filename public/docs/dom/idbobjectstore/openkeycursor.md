# IDBObjectStore.openKeyCursor()

The `openKeyCursor()` method of the [`IDBObjectStore`](../idbobjectstore) interface returns an [`IDBRequest`](../idbrequest) object whose result will be set to an [`IDBCursor`](../idbcursor) that can be used to iterate through matching results. Used for iterating through the keys of an object store with a cursor.

To determine if the add operation has completed successfully, listen for the results’s `success` event.

## Syntax

    var request = objectStore.openKeyCursor();
    var request = objectStore.openKeyCursor(query);
    var request = objectStore.openKeyCursor(query, direction);

### Parameters

_query_ <span class="badge inline optional">Optional</span>  
The key range to be queried. If a single valid key is passed, this will default to a range containing only that key. If nothing is passed, this will default to a key range that selects all the records in this object store.

_direction_ <span class="badge inline optional">Optional</span>  
An [`IDBCursorDirection`](https://w3c.github.io/IndexedDB/#enumdef-idbcursordirection) telling the cursor what direction to travel. Valid values are `"next"`, `"nextunique"`, `"prev"`, and `"prevunique"`. The default is `"next"`.

### Return value

An [`IDBRequest`](../idbrequest) object on which subsequent events related to this operation are fired.

### Exceptions

This method may raise a [`DOMException`](../domexception) of one of the following types:

<table><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>InvalidStateError</code></td><td>This <a href="../idbobjectstore"><code>IDBObjectStore</code></a> or <a href="../idbindex"><code>IDBIndex</code></a> has been deleted.</td></tr><tr class="even"><td><code>TransactionInactiveError</code></td><td>This <a href="../idbobjectstore"><code>IDBObjectStore</code></a>'s transaction is inactive.</td></tr><tr class="odd"><td><code>DataError</code></td><td>The specified key or key range is invalid.<br />
</td></tr></tbody></table>

## Example

In this simple fragment we create a transaction, retrieve an object store, then use a cursor to iterate through all the records in the object store:

    var transaction = db.transaction("name", "readonly");
    var objectStore = transaction.objectStore("name");
    var request = objectStore.openKeyCursor();
    request.onsuccess = function(event) {
      var cursor = event.target.result;
      if(cursor) {
        // cursor.key contains the key of the current record being iterated through
        // note that there is no cursor.value, unlike for openCursor
        // this is where you'd do something with the result
        cursor.continue();
      } else {
        // no more results
      }
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbobjectstore-openkeycursor">Indexed Database API 2.0<br />
<span class="small">The definition of 'openKeyCursor()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbobjectstore-openkeycursor">Indexed Database API 2.0<br />
<span class="small">The definition of 'openKeyCursor()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`openKeyCursor`

23

12

44

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/openKeyCursor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/openKeyCursor</a>
