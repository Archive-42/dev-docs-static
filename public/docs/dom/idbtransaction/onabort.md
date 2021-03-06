# IDBTransaction.onabort

The `onabort` event handler of the `IDBTransaction` interface handles the abort event, fired, when the current transaction is aborted via the [`IDBTransaction.abort`](abort) method.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    transaction.onabort = function(event) { ... };

## Example

In the following code snippet, we open a read/write transaction on our database and add some data to an object store. Note also the functions attached to transaction event handlers to report on the outcome of the transaction opening in the event of success or failure. Note the `transaction.onabort = function(event) { };` block, reporting when the transaction has been aborted. For a full working example, see our [To-do Notifications](https://github.com/mdn/to-do-notifications/)<span style="line-height: 1.5;"> app (</span>[view example live](https://mdn.github.io/to-do-notifications/)<span style="line-height: 1.5;">.)</span>

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
      // Create a new object ready for being inserted into the IDB
      var newItem = [ { taskTitle: "Walk dog", hours: 19, minutes: 30, day: 24, month: "December", year: 2013, notified: "no" } ];

      // open a read/write db transaction, ready for adding the data
      var transaction = db.transaction(["toDoList"], "readwrite");

      // report on the success of opening the transaction
      transaction.oncomplete = function(event) {
        note.innerHTML += '<li>Transaction completed: database modification finished.</li>';
      };

      transaction.onerror = function(event) {
        note.innerHTML += '<li>Transaction not opened due to error: ' + transaction.error + '</li>';
      };

      // create an object store on the transaction
      var objectStore = transaction.objectStore("toDoList");

      // add our newItem object to the object store
      var objectStoreRequest = objectStore.add(newItem[0]);

      objectStoreRequest.onsuccess = function(event) {
        // report the success of the request (this does not mean the item
        // has been stored successfully in the DB - for that you need transaction.onsuccess)
        note.innerHTML += '<li>Request successful.</li>';
      };

      transaction.onabort = function() {
        // Report when the transaction was successfully aborted
        console.log("Transaction aborted!");
      };

      // Abort the transaction we just did
      transaction.abort();
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbtransaction-onabort">Indexed Database API 2.0<br />
<span class="small">The definition of 'onabort' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbtransaction-onabort">Indexed Database API 2.0<br />
<span class="small">The definition of 'onabort' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`onabort`

23

12

10

10

15

7

???37

Yes

22

14

8

Yes

## See also

- [Using IndexedDB](../indexeddb_api/using_indexeddb)
- Starting transactions: [`IDBDatabase`](../idbdatabase)
- Using transactions: [`IDBTransaction`](../idbtransaction)
- Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
- Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
- Using cursors: [`IDBCursor`](../idbcursor)
- Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)
- `IDBTransaction` `abort` event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBTransaction/onabort" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBTransaction/onabort</a>
