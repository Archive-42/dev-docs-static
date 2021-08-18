# IDBObjectStore.name

The `name` property of the [`IDBObjectStore`](../idbobjectstore) interface indicates the name of this object store.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    IDBObjectStore.name = myNewName;
    var myObjectStoreName = IDBObjectStore.name;

### Value

<span style="line-height: 1.5;">A [`DOMString`](../domstring) containing the object store's name.</span>

### Exceptions

There are a several exceptions which can occur when you attempt to change an object store's name.

`InvalidStateError`  
Either the object store has been deleted or the current transaction is not an upgrade transaction; you can only rename indexes during upgrade transactions; that is, when the mode is `"versionchange"`.

`TransactionInactiveError`  
The current transaction is not active.

`ConstraintError`  
An object store is already using the specified `name`.

## Example

In the following code snippet, we open a read/write transaction on our database and add some data to an object store using `add()`. After the object store has been created, we log objectStore.name to the console. <span style="line-height: 1.5;">For a full working example, see our </span>[To-do Notifications](https://github.com/mdn/to-do-notifications/)<span style="line-height: 1.5;"> app (</span>[view example live](https://mdn.github.io/to-do-notifications/)<span style="line-height: 1.5;">.)</span>

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
      console.log(objectStore.name);

      // Make a request to add our newItem object to the object store
      var objectStoreRequest = objectStore.add(newItem[0]);

      objectStoreRequest.onsuccess = function(event) {
        // report the success of our request
        note.innerHTML += '<li>Request successful.</li>';
      };
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbobjectstore-name">Indexed Database API 2.0<br />
<span class="small">The definition of 'name' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbobjectstore-name">Indexed Database API 2.0<br />
<span class="small">The definition of 'name' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`name`

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

`renaming_through_name_setter`

Yes

≤18

49

?

Yes

?

Yes

Yes

49

Yes

?

Yes

## See also

- [Using IndexedDB](../indexeddb_api/using_indexeddb)
- Starting transactions: [`IDBDatabase`](../idbdatabase)
- Using transactions: [`IDBTransaction`](../idbtransaction)
- Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
- Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
- Using cursors: [`IDBCursor`](../idbcursor)
- Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/name" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/name</a>
