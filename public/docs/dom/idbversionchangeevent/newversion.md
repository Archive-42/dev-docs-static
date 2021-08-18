# IDBVersionChangeEvent.newVersion

The `newVersion` read-only property of the [`IDBVersionChangeEvent`](../idbversionchangeevent) interface returns the new version number of the database.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    var newVersion = IDBVersionChangeEvent.newVersion

### Value

A [64-bit integer](<https://developer.mozilla.org/en-US/docs/NSPR_API_Reference/Long_Long_(64-bit)_Integers>).

## Example

In the following code snippet, we make a request to open a database, and include handlers for the success and error cases. These events are fired via the custom `IDBVersionChangeEvent` interface. For a full working example, see our [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) app ([view example live](https://mdn.github.io/to-do-notifications/).)

    var note = document.querySelector("ul");

    // In the following line, you should include the prefixes of
    // implementations you want to test.
    window.indexedDB = window.indexedDB || window.mozIndexedDB || window.webkitIndexedDB || window.msIndexedDB;
    // DON'T use "var indexedDB = ..." if you're not in a function.
    // Moreover, you may need references to some window.IDB* objects:
    window.IDBTransaction = window.IDBTransaction || window.webkitIDBTransaction || window.msIDBTransaction;
    window.IDBKeyRange = window.IDBKeyRange || window.webkitIDBKeyRange || window.msIDBKeyRange;
    // (Mozilla has never prefixed these objects,
    //  so we don't need window.mozIDB*)

    // Let us open version 4 of our database
    var DBOpenRequest = window.indexedDB.open("toDoList", 4);

    // these two event handlers act on the database being opened
    DBOpenRequest.onerror = function(event) {
      note.innerHTML += '<li>Error loading database.</li>';
    };

    DBOpenRequest.onsuccess = function(event) {
      note.innerHTML += '<li>Database initialised.</li>';

      // store the result of opening the database in the db variable.
      // This is used a lot later on, for opening transactions and suchlike.
      db = DBOpenRequest.result;
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbversionchangeevent-newversion">Indexed Database API 2.0<br />
<span class="small">The definition of 'newVersion' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbversionchangeevent-newversion">Indexed Database API 2.0<br />
<span class="small">The definition of 'newVersion' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`newVersion`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBVersionChangeEvent/newVersion" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBVersionChangeEvent/newVersion</a>
