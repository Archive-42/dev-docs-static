# IDBObjectStore.add()

The `add()` method of the [`IDBObjectStore`](../idbobjectstore) interface returns an [`IDBRequest`](../idbrequest) object, and, in a separate thread, creates a [structured clone](https://www.whatwg.org/specs/web-apps/current-work/multipage/common-dom-interfaces.html#structured-clone) of the value, and stores the cloned value in the object store. This is for adding new records to an object store.

To determine if the add operation has completed successfully, listen for the transaction’s `complete` event in addition to the `IDBObjectStore.add` request’s `success` event, because the transaction may still fail after the success event fires. In other words, the success event is only triggered when the transaction has been successfully queued.

The add method is an<span class="database"> _insert only_ </span>method. If a record already exists in the object store with the `key` parameter as its key, then an error `ConstrainError` event is fired on the returned request object. For updating existing records, you should use the [`IDBObjectStore.put`](put) method instead.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    var request = objectStore.add(value);
    var request = objectStore.add(value, key);

### Parameters

value  
The value to be stored.

key <span class="badge inline optional">Optional</span>  
The key to use to identify the record. If unspecified, it results to null.

### Returns

<span style="line-height: 1.5;">An </span><span style="line-height: 1.5;">[`IDBRequest`](../idbrequest)</span><span style="line-height: 1.5;"> object on</span><span style="line-height: 1.5;"> which subsequent events related to this operation are fired.</span>

### Exceptions

<span style="line-height: 1.5;">This method may raise a [`DOMException`](../domexception) of one of the following types:</span>

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>ReadOnlyError</code></td><td>The transaction associated with this operation is in read-only <a href="../idbtransaction#mode_constants">mode</a>.</td></tr><tr class="even"><td><code>TransactionInactiveError</code></td><td>This <a href="../idbobjectstore"><code>IDBObjectStore</code></a>'s transaction is inactive.</td></tr><tr class="odd"><td><code>DataError</code></td><td><p>Any of the following conditions apply:</p><ul><li>The object store uses in-line keys or has a key generator, and a key parameter was provided.</li><li>The object store uses out-of-line keys and has no key generator, and no key parameter was provided.</li><li>The object store uses in-line keys but no key generator, and the object store's key path does not yield a valid key.</li><li>The key parameter was provided but does not contain a valid key.</li></ul></td></tr><tr class="even"><td><code>InvalidStateError</code></td><td>The <a href="../idbobjectstore"><code>IDBObjectStore</code></a> has been deleted or removed.</td></tr><tr class="odd"><td><code>DataCloneError</code></td><td>The data being stored could not be cloned by the internal structured cloning algorithm.<br />
</td></tr><tr class="even"><td><code class="idl">ConstraintError</code></td><td>An insert operation failed because the primary key constraint was violated (due to an already existing record with the same primary key value).</td></tr></tbody></table>

## Example

In the following code snippet, we open a read/write transaction on our database and add some data to an object store using `add()`. Note also the functions attached to transaction event handlers to report on the outcome of the transaction opening in the event of success or failure. For a full working example, see our [To-do Notifications](https://github.com/mdn/to-do-notifications/)<span style="line-height: 1.5;"> app (</span>[view example live](https://mdn.github.io/to-do-notifications/)<span style="line-height: 1.5;">.)</span>

    // Let us open our database
    var DBOpenRequest = window.indexedDB.open("toDoList", 4);

    DBOpenRequest.onsuccess = function(event) {
      note.innerHTML += '<li>Database initialised.</li>';

      // store the result of opening the database in the db variable.
      // This is used a lot below
      db = DBOpenRequest.result;

      // Run the addData() function to add the data to the database
      addData();
    };

    function addData() {
      // Create a new object ready to insert into the IDB
      var newItem = [ { taskTitle: "Walk dog", hours: 19, minutes: 30, day: 24, month: "December", year: 2013, notified: "no" } ];

      // open a read/write db transaction, ready for adding the data
      var transaction = db.transaction(["toDoList"], "readwrite");

      // report on the success of the transaction completing, when everything is done
      transaction.oncomplete = function(event) {
        note.innerHTML += '<li>Transaction completed.</li>';
      };

      transaction.onerror = function(event) {
      note.innerHTML += '<li>Transaction not opened due to error. Duplicate items not allowed.</li>';
      };

      // create an object store on the transaction
      var objectStore = transaction.objectStore("toDoList");

      // Make a request to add our newItem object to the object store
      var objectStoreRequest = objectStore.add(newItem[0]);

      objectStoreRequest.onsuccess = function(event) {
        // report the success of our request
        note.innerHTML += '<li>Request successful.</li>';
      };
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbobjectstore-add">Indexed Database API 2.0<br />
<span class="small">The definition of 'add()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbobjectstore-add">Indexed Database API 2.0<br />
<span class="small">The definition of 'add()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`add`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/add" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/add</a>
