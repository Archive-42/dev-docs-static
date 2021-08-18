IDBObjectStore
==============

The `IDBObjectStore` interface of the [IndexedDB API](indexeddb_api) represents an object store in a database. Records within an object store are sorted according to their keys. This sorting enables fast insertion, look-up, and ordered retrieval.

**Note:** This feature is available in [Web Workers](web_workers_api).

Properties
----------

 [`IDBObjectStore.indexNames`](idbobjectstore/indexnames) <span class="badge inline readonly">Read only </span>   
A list of the names of [indexes](indexeddb_api#gloss_index) on objects in this object store.

 [`IDBObjectStore.keyPath`](idbobjectstore/keypath) <span class="badge inline readonly">Read only </span>   
The [key path](indexeddb_api#gloss_key_path) of this object store. If this attribute is `null`, the application must provide a key for each modification operation.

[`IDBObjectStore.name`](idbobjectstore/name)  
The name of this object store.

 [`IDBObjectStore.transaction`](idbobjectstore/transaction) <span class="badge inline readonly">Read only </span>   
The [`IDBTransaction`](idbtransaction) object to which this object store belongs.

 [`IDBObjectStore.autoIncrement`](idbobjectstore/autoincrement) <span class="badge inline readonly">Read only </span>   
The value of the auto increment flag for this object store.

Methods
-------

[`IDBObjectStore.add()`](idbobjectstore/add)  
Returns an [`IDBRequest`](idbrequest) object, and, in a separate thread, creates a [structured clone](https://www.whatwg.org/specs/web-apps/current-work/multipage/common-dom-interfaces.html#structured-clone) of the `value`, and stores the cloned value in the object store. This is for adding new records to an object store.

[`IDBObjectStore.clear()`](idbobjectstore/clear)  
Creates and immediately returns an [`IDBRequest`](idbrequest) object, and clears this object store in a separate thread. This is for deleting all current records out of an object store.

[`IDBObjectStore.count()`](idbobjectstore/count)  
Returns an [`IDBRequest`](idbrequest) object, and, in a separate thread, returns the total number of records that match the provided key or [`IDBKeyRange`](idbkeyrange). If no arguments are provided, it returns the total number of records in the store.

[`IDBObjectStore.createIndex()`](idbobjectstore/createindex)  
Creates a new index during a version upgrade, returning a new [`IDBIndex`](idbindex) object in the connected database.

[`IDBObjectStore.delete()`](idbobjectstore/delete)  
returns an [`IDBRequest`](idbrequest) object, and, in a separate thread, deletes the store object selected by the specified key. This is for deleting individual records out of an object store.

[`IDBObjectStore.deleteIndex()`](idbobjectstore/deleteindex)  
Destroys the specified index in the connected database, used during a version upgrade.

[`IDBObjectStore.get()`](idbobjectstore/get)  
Returns an [`IDBRequest`](idbrequest) object, and, in a separate thread, returns the store object store selected by the specified key. This is for retrieving specific records from an object store.

[`IDBObjectStore.getKey()`](idbobjectstore/getkey)  
Returns an [`IDBRequest`](idbrequest) object, and, in a separate thread retrieves and returns the record key for the object in the object stored matching the specified parameter.

[`IDBObjectStore.getAll()`](idbobjectstore/getall)  
Returns an [`IDBRequest`](idbrequest) object retrieves all objects in the object store matching the specified parameter or all objects in the store if no parameters are given.

[`IDBObjectStore.getAllKeys()`](idbobjectstore/getallkeys)  
Returns an [`IDBRequest`](idbrequest) object retrieves record keys for all objects in the object store matching the specified parameter or all objects in the store if no parameters are given.

[`IDBObjectStore.index()`](idbobjectstore/index)  
Opens an index from this object store after which it can, for example, be used to return a sequence of records sorted by that index using a cursor.

[`IDBObjectStore.openCursor()`](idbobjectstore/opencursor)  
Returns an [`IDBRequest`](idbrequest) object, and, in a separate thread, returns a new [`IDBCursorWithValue`](idbcursorwithvalue) object. Used for iterating through an object store by primary key with a cursor.

 [`IDBObjectStore.openKeyCursor()`](idbobjectstore/openkeycursor)   
Returns an [`IDBRequest`](idbrequest) object, and, in a separate thread, returns a new [`IDBCursor`](idbcursor). Used for iterating through an object store with a key.

[`IDBObjectStore.put()`](idbobjectstore/put)  
Returns an [`IDBRequest`](idbrequest) object, and, in a separate thread, creates a [structured clone](https://www.whatwg.org/specs/web-apps/current-work/multipage/common-dom-interfaces.html#structured-clone) of the `value`, and stores the cloned value in the object store. This is for updating existing records in an object store when the transaction's mode is `readwrite`.

Example
-------

This example shows a variety of different uses of object stores, from updating the data structure with [`IDBObjectStore.createIndex`](idbobjectstore/createindex) inside an `onupgradeneeded` function, to adding a new item to our object store with [`IDBObjectStore.add`](idbobjectstore/add). For a full working example, see our [To-do Notifications](https://github.com/mdn/to-do-notifications/)<span style="line-height: 1.5;"> app (</span>[view example live](https://mdn.github.io/to-do-notifications/)<span style="line-height: 1.5;">.)</span>

    // Let us open our database
    var DBOpenRequest = window.indexedDB.open("toDoList", 4);

    DBOpenRequest.onsuccess = function(event) {
      note.innerHTML += '<li>Database initialised.</li>';

      // store the result of opening the database in db.
      db = DBOpenRequest.result;
    };

    // This event handles the event whereby a new version of
    // the database needs to be created Either one has not
    // been created before, or a new version number has been
    // submitted via the window.indexedDB.open line above
    DBOpenRequest.onupgradeneeded = function(event) {
      var db = event.target.result;

      db.onerror = function(event) {
        note.innerHTML += '<li>Error loading database.</li>';
      };

      // Create an objectStore for this database

      var objectStore = db.createObjectStore("toDoList", { keyPath: "taskTitle" });

      // define what data items the objectStore will contain

      objectStore.createIndex("hours", "hours", { unique: false });
      objectStore.createIndex("minutes", "minutes", { unique: false });
      objectStore.createIndex("day", "day", { unique: false });
      objectStore.createIndex("month", "month", { unique: false });
      objectStore.createIndex("year", "year", { unique: false });

      objectStore.createIndex("notified", "notified", { unique: false });

      note.innerHTML += '<li>Object store created.</li>';
    };

    // Create a new item to add in to the object store
    var newItem = [
      { taskTitle: "Walk dog", hours: 19, minutes: 30, day: 24, month: 'December', year: 2013, notified: "no" }
    ];

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
    // make a request to add our newItem object to the object store
    var objectStoreRequest = objectStore.add(newItem[0]);

    objectStoreRequest.onsuccess = function(event) {
      note.innerHTML += '<li>Request successful .</li>';
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#idbobjectstore">Indexed Database API 2.0<br />
<span class="small">The definition of 'IDBObjectStore' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#object-store-interface">Indexed Database API 2.0<br />
<span class="small">The definition of 'IDBObjectStore' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`IDBObjectStore`

24

23-57

12

16

10-16

10

15

7

≤37

≤37-57

25

25-57

22

14

8

1.5

1.5-7.0

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

`autoIncrement`

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

`clear`

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

`count`

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

`createIndex`

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

`delete`

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

`deleteIndex`

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

`get`

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

`getAll`

48

≤79

44

No

35

10.1

48

48

48

35

10.3

5.0

`getAllKeys`

48

≤79

44

No

35

10.1

48

48

48

35

10.3

5.0

`getKey`

48

≤79

51

No

45

10.1

48

48

58

43

10.3

5.0

`index`

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

`indexNames`

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

`keyPath`

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

`openCursor`

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

`put`

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

`worker_support`

Yes

≤18

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

See also
--------

-   [Using IndexedDB](indexeddb_api/using_indexeddb)
-   Starting transactions: [`IDBDatabase`](idbdatabase)
-   Using transactions: [`IDBTransaction`](idbtransaction)
-   Setting a range of keys: [`IDBKeyRange`](idbkeyrange)
-   Retrieving and making changes to your data: [`IDBObjectStore`](idbobjectstore)
-   Using cursors: [`IDBCursor`](idbcursor)
-   Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore</a>
