IDBDatabase.transaction()
=========================

The `transaction` method of the [`IDBDatabase`](../idbdatabase) interface immediately returns a transaction object ([`IDBTransaction`](../idbtransaction)) containing the [`IDBTransaction.objectStore`](../idbtransaction/objectstore) method, which you can use to access your object store.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    IDBDatabase.transaction(storeNames);
    IDBDatabase.transaction(storeNames, mode);
    IDBDatabase.transaction(storeNames, mode, options);

### Parameters

`storeNames`  
The names of object stores that are in the scope of the new transaction, declared as an array of strings. Specify only the object stores that you need to access.  
If you need to access only one object store, you can specify its name as a string. Therefore the following lines are equivalent:

    var transaction = db.transaction(['my-store-name']);
    var transaction = db.transaction('my-store-name');

If you need to access all object stores in the database, you can use the property [`IDBDatabase.objectStoreNames`](objectstorenames):

    var transaction = db.transaction(db.objectStoreNames);

Passing an empty array will throw an exception.

 `mode` <span class="badge inline optional">Optional</span>   
The types of access that can be performed in the transaction. Transactions are opened in one of three modes: `readonly`, `readwrite` and `readwriteflush` (non-standard, Firefox-only.) `versionchange` mode can't be specified here. If you don't provide the parameter, the default access mode is `readonly`. To avoid slowing things down, don't open a `readwrite` transaction unless you actually need to write into the database.

If you need to open the object store in `readwrite` mode to change data, you would use the following:

    var transaction = db.transaction('my-store-name', "readwrite");

As of Firefox 40, IndexedDB transactions have relaxed durability guarantees to increase performance (see [bug 1112702](https://bugzilla.mozilla.org/show_bug.cgi?id=1112702)), which is the same behavior as other IndexedDB-supporting browsers. Previously in a `readwrite` transaction [`IDBTransaction.oncomplete`](../idbtransaction/oncomplete) was fired only when all data was guaranteed to have been flushed to disk. In Firefox 40+ the `complete` event is fired after the OS has been told to write the data but potentially before that data has actually been flushed to disk. The `complete` event may thus be delivered quicker than before, however, there exists a small chance that the entire transaction will be lost if the OS crashes or there is a loss of system power before the data is flushed to disk. Since such catastrophic events are rare most consumers should not need to concern themselves further.

**Note**: In Firefox, if you wish to ensure durability for some reason (e.g. you're storing critical data that cannot be recomputed later) you can force a transaction to flush to disk before delivering the `complete` event by creating a transaction using the experimental (non-standard) `readwriteflush` mode (see [`IDBDatabase.transaction`](transaction).) This is currently experimental, and can only be used if the `dom.indexedDB.experimental` pref is set to `true` in `about:config`.

 `options` <span class="badge inline optional">Optional</span>   
Dictionary of other options. Available options are:

-   `durability`: `"default"`, `"strict"`, or `"relaxed"`. The default is `"default"`. Using `"relaxed"` provides better performance, but with fewer guarantees. Web applications are encouraged to use `"relaxed"` for ephemeral data such as caches or quickly changing records, and `"strict"` in cases where reducing the risk of data loss outweighs the impact to performance and power.

### Return value

An [`IDBTransaction`](../idbtransaction) object.

### Exceptions

This method may raise a [`DOMException`](../domexception) of one of the following types:

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>InvalidStateError</code></td><td><p>The <code>close()</code> method has previously been called on this <a href="../idbdatabase"><code>IDBDatabase</code></a> instance.</p></td></tr><tr class="even"><td><code>NotFoundError</code></td><td>An object store specified in the <code>storeNames</code> parameter has been deleted or removed.</td></tr><tr class="odd"><td><code>TypeError</code></td><td>The value for the <code>mode</code> parameter is invalid.</td></tr><tr class="even"><td><code>InvalidAccessError</code></td><td>The function was called with an empty list of store names.<br />
</td></tr></tbody></table>

Example
-------

In this example we open a database connection, then use transaction() to open a transaction on the database. For a complete example, see our [To-do Notifications](https://github.com/mdn/to-do-notifications/) app ([view example live](https://mdn.github.io/to-do-notifications/).)

    var db;

    // Let us open our database
    var DBOpenRequest = window.indexedDB.open("toDoList", 4);

    DBOpenRequest.onsuccess = function(event) {
      note.innerHTML += '<li>Database initialised.</li>';

      // store the result of opening the database in the db variable.
      // This is used a lot below
      db = DBOpenRequest.result;

      // Run the displayData() function to populate the task list with
      // all the to-do list data already in the IDB
      displayData();

    };

    // open a read/write db transaction, ready for adding the data
    var transaction = db.transaction(["toDoList"], "readwrite");

    // report on the success of opening the transaction
    transaction.oncomplete = function(event) {
      note.innerHTML += '<li>Transaction completed: database modification finished.</li>';
    };

    transaction.onerror = function(event) {
      note.innerHTML += '<li>Transaction not opened due to error. Duplicate items not allowed.</li>';
    };

    // you would then go on to do something to this database
    // via an object store
    var objectStore = transaction.objectStore("toDoList");
    // etc.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbdatabase-transaction">Indexed Database API 2.0<br />
<span class="small">The definition of 'transaction()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbdatabase-transaction">Indexed Database API 2.0<br />
<span class="small">The definition of 'transaction()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`transaction`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/transaction" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/transaction</a>
