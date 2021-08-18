IDBRequest.transaction
======================

The `transaction` read-only property of the IDBRequest interface returns the transaction for the request, that is, the transaction the request is being made inside.

This property can be `null` for requests not made within transactions, such as for requests returned from [`IDBFactory.open`](../idbfactory/open) — in this case you're just connecting to a database, so there is no transaction to return. If a version upgrade is needed when opening a database then during the [`upgradeneeded`](../idbopendbrequest/onupgradeneeded) event handler the `transaction` property will be an [`IDBTransaction`](../idbtransaction) with [`mode`](../idbtransaction/mode) equal to `"versionchange"`, and can be used to access existing object stores and indexes, or abort the upgrade. Following the upgrade, the `transaction` property will again be `null`.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var myTransaction = request.transaction;

### Value

An [`IDBTransaction`](../idbtransaction).

Example
-------

The following example requests a given record title, `onsuccess` gets the associated record from the [`IDBObjectStore`](../idbobjectstore) (made available as `objectStoreTitleRequest.result`<span style="line-height: 1.5;">), updates one property of the record, and then puts the updated record back into the object store in another request. The source of the requests is logged to the developer console — both originate from the same transaction. For a full working example, see our </span>[To-do Notifications](https://github.com/mdn/to-do-notifications/)<span style="line-height: 1.5;"> app (</span>[view example live](https://mdn.github.io/to-do-notifications/)<span style="line-height: 1.5;">.)</span>

    var title = "Walk dog";

    // Open up a transaction as usual
    var objectStore = db.transaction(['toDoList'], "readwrite").objectStore('toDoList');

    // Get the to-do list object that has this title as it's title
    var objectStoreTitleRequest = objectStore.get(title);

    objectStoreTitleRequest.onsuccess = function() {
      // Grab the data object returned as the result
      var data = objectStoreTitleRequest.result;

      // Update the notified value in the object to "yes"
      data.notified = "yes";

      // Create another request that inserts the item back
      // into the database
      var updateTitleRequest = objectStore.put(data);

      // Log the transaction that originated this request
      console.log("The transaction that originated this request is " + updateTitleRequest.transaction);

      // When this new request succeeds, run the displayData()
      // function again to update the display
      updateTitleRequest.onsuccess = function() {
        displayData();
      };
    };

This example shows how a the `transaction` property can be used during a version upgrade to access existing object stores:

    var openRequest = indexedDB.open('db', 2);
    console.log(openRequest.transaction); // Will log "null".

    openRequest.onupgradeneeded = function(event) {
      console.log(openRequest.transaction.mode); // Will log "versionchange".
      var db = openRequest.result;
      if (event.oldVersion < 1) {
        // New database, create "books" object store.
        db.createObjectStore('books');
      }
      if (event.oldVersion < 2) {
        // Upgrading from v1 database: add index on "title" to "books" store.
        var bookStore = openRequest.transaction.objectStore('books');
        bookStore.createIndex('by_title', 'title');
      }
    };

    openRequest.onsuccess = function() {
      console.log(openRequest.transaction); // Will log "null".
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbrequest-transaction">Indexed Database API 2.0<br />
<span class="small">The definition of 'transaction' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbrequest-transaction">Indexed Database API 2.0<br />
<span class="small">The definition of 'transaction' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

Yes

22

14

8

Yes

See also
--------

-   [Using IndexedDB](../indexeddb_api/using_indexeddb)
-   Starting transactions: [`IDBDatabase`](../idbdatabase)
-   Using transactions: [`IDBTransaction`](../idbtransaction)
-   Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
-   Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
-   Using cursors: [`IDBCursor`](../idbcursor)
-   Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBRequest/transaction" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBRequest/transaction</a>
