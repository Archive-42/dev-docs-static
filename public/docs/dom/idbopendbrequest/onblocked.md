# IDBOpenDBRequest.onblocked

The `onblocked `event handler of the [`IDBOpenDBRequest`](../idbopendbrequest) interface is the event handler for the `blocked` event. This event is triggered when the `upgradeneeded` should be triggered because of a version change but the database is still in use (that is, not closed) somewhere, even after the `versionchange` event was sent.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    IDBOpenDBRequest.onblocked = function(event) { ... };

## Example

    var db;

    // Let us open our database
    var request = indexedDB.open("toDoList", 4);

    // these two event handlers act on the database being opened
    // successfully, or not
    request.onerror = function(event) {
      note.innerHTML += '<li>Error loading database.</li>';
    };

    request.onsuccess = function(event) {
      note.innerHTML += '<li>Database initialised.</li>';

      // store the result of opening the database in the db variable.
      // This is used a lot below
      db = request.result;

      // Run the displayData() function to populate the task list with
      // all the to-do list data already in the IDB
      displayData();
    };

    // This event handles the event whereby a new version of the
    // database needs to be created. Either one has not been created
    // before, or a new version number has been submitted via the
    // window.indexedDB.open line above
    //it is only implemented in recent browsers
    request.onupgradeneeded = function(event) {
      var db = event.target.result;

      db.onerror = function(event) {
        note.innerHTML += '<li>Error loading database.</li>';
      };

      // Create an objectStore for this database
      var objectStore = db.createObjectStore("toDoList", { keyPath: "taskTitle" });

      ...
    };

    request.onblocked = function() {
      console.log("Your database version can't be upgraded because the app is open somewhere else.");
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbopendbrequest-onblocked">Indexed Database API 2.0<br />
<span class="small">The definition of 'onblocked' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbopendbrequest-onblocked">Indexed Database API 2.0<br />
<span class="small">The definition of 'onblocked' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`onblocked`

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
- `blocked` event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBOpenDBRequest/onblocked" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBOpenDBRequest/onblocked</a>
