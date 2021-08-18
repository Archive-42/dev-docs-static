# IDBVersionChangeEvent

The `IDBVersionChangeEvent` interface of the [IndexedDB API](indexeddb_api) indicates that the version of the database has changed, as the result of an [`IDBOpenDBRequest.onupgradeneeded`](idbopendbrequest/onupgradeneeded) event handler function.

**Note:** This feature is available in [Web Workers](web_workers_api).

## Constructor

[`IDBVersionChangeEvent()`](idbversionchangeevent/idbversionchangeevent)  
Creates and returns a new `IDBVersionChangeEvent` object which is used to represent when a version of the database has changed.

## Properties

_Also inherits properties from its parent, [`Event`](event) interface._

[`IDBVersionChangeEvent.oldVersion`](idbversionchangeevent/oldversion) <span class="badge inline readonly">Read only </span>  
Returns the old version of the database.

[`IDBVersionChangeEvent.newVersion`](idbversionchangeevent/newversion) <span class="badge inline readonly">Read only </span>  
Returns the new version of the database.

### Deprecated properties

[`IDBVersionChangeEvent.version`](idbversionchangeevent/version) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
The new version of the database in a `versionchange` transaction.

**Warning**: While this property is still implemented in older browsers, the latest specification replaces it with the `oldVersion` and `newVersion` attributes. See the compatibility table to know what browsers support them.

### Methods

_No specific method, but inherits properties from its parent, [`Event`](event) interface._

## Example

In the following code snippet, we make a request to open a database, and include handlers for the success and error cases. Upon a version change (after an `upgradedneeded` event), the `success` event will implement the `IDBVersionChangeEvent` interface. For a full working example, see our [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) app ([view example live](https://mdn.github.io/to-do-notifications/).)

    var note = document.querySelector("ul");

    // In the following line, you should include the prefixes of implementations you want to test.
    window.indexedDB = window.indexedDB || window.mozIndexedDB || window.webkitIndexedDB || window.msIndexedDB;
    // DON'T use "var indexedDB = ..." if you're not in a function.
    // Moreover, you may need references to some window.IDB* objects:
    window.IDBTransaction = window.IDBTransaction || window.webkitIDBTransaction || window.msIDBTransaction;
    window.IDBKeyRange = window.IDBKeyRange || window.webkitIDBKeyRange || window.msIDBKeyRange;
    // (Mozilla has never prefixed these objects, so we don't need window.mozIDB*)

    // Let us open version 4 of our database
    var DBOpenRequest = window.indexedDB.open("toDoList", 4);

    // these two event handlers act on the database being opened successfully, or not
    DBOpenRequest.onerror = function(event) {
      note.innerHTML += '<li>Error loading database.</li>';
    };

    DBOpenRequest.onsuccess = function(event) {
      note.innerHTML += '<li>Database initialised.</li>';

      // store the result of opening the database in the db variable. This is used a lot later on, for opening transactions and suchlike.
      db = DBOpenRequest.result;
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#idbversionchangeevent">Indexed Database API 2.0<br />
<span class="small">The definition of 'IDBVersionChangeEvent' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#idbversionchangeevent">Indexed Database API 2.0<br />
<span class="small">The definition of 'IDBVersionChangeEvent' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`IDBVersionChangeEvent`

24

12

12

16

10-16

10

15

7

≤37

≤37

Yes

22

Yes

Yes

Yes

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

`oldVersion`

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

`version`

12

≤18

10

No

No

No

≤37

18

22

22

No

1.0

`worker_support`

Yes

≤79

37

?

Yes

?

Yes

Yes

37

Yes

?

Yes

## See also

- [Using IndexedDB](indexeddb_api/using_indexeddb)
- Starting transactions: [`IDBDatabase`](idbdatabase)
- Using transactions: [`IDBTransaction`](idbtransaction)
- Setting a range of keys: [`IDBKeyRange`](idbkeyrange)
- Retrieving and making changes to your data: [`IDBObjectStore`](idbobjectstore)
- Using cursors: [`IDBCursor`](idbcursor)
- [IDBDatabase.onversionchange](idbdatabase/onversionchange)
- Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBVersionChangeEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBVersionChangeEvent</a>
