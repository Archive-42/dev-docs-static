IDBDatabase
===========

The `IDBDatabase` interface of the IndexedDB API provides a [connection to a database](indexeddb_api#database_connection); you can use an `IDBDatabase` object to open a [transaction](indexeddb_api#gloss_transaction) on your database then create, manipulate, and delete objects (data) in that database. The interface provides the only way to get and manage versions of the database.

**Note:** This feature is available in [Web Workers](web_workers_api).

**Note**: Everything you do in IndexedDB always happens in the context of a [transaction](indexeddb_api/basic_concepts_behind_indexeddb#gloss_transaction), representing interactions with data in the database. All objects in IndexedDB — including object stores, indexes, and cursors — are tied to a particular transaction. Thus, you cannot execute commands, access data, or open anything outside of a transaction.

Properties
----------

 [`IDBDatabase.name`](idbdatabase/name) <span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) that contains the name of the connected database.

 [`IDBDatabase.version`](idbdatabase/version) <span class="badge inline readonly">Read only </span>   
A [64-bit integer](https://developer.mozilla.org/en-US/docs/NSPR_API_Reference/Long_Long_(64-bit)_Integers) that contains the version of the connected database. When a database is first created, this attribute is an empty string.

 [`IDBDatabase.objectStoreNames`](idbdatabase/objectstorenames) <span class="badge inline readonly">Read only </span>   
A [`DOMStringList`](domstringlist) that contains a list of the names of the [object stores](indexeddb_api#gloss_object_store) currently in the connected database.

Methods
-------

Inherits from: [EventTarget](eventtarget)

[`IDBDatabase.close()`](idbdatabase/close)  
Returns immediately and closes the connection to a database in a separate thread.

<span class="page-not-created">`IDBDatabase.createMutableFile()`</span>  
Creates a file handle, allowing files to be stored inside an IndexedDB database.

[`IDBDatabase.createObjectStore()`](idbdatabase/createobjectstore)  
Creates and returns a new object store or index.

[`IDBDatabase.deleteObjectStore()`](idbdatabase/deleteobjectstore)  
Destroys the object store with the given name in the connected database, along with any indexes that reference it.

[`IDBDatabase.transaction()`](idbdatabase/transaction)  
Immediately returns a transaction object ([`IDBTransaction`](idbtransaction)) containing the [`IDBTransaction.objectStore`](idbtransaction/objectstore) method, which you can use to access your object store. Runs in a separate thread.

Events
------

Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

[`abort`](idbdatabase/abort_event)  
Fired when a transaction is aborted and bubbles up to the connection object. Also available via the `onabort` property.

[`close`](idbdatabase/close_event)  
Fired when the database connection is unexpectedly closed. Also available via the `onclose` property.

[`error`](idbdatabase/error_event)  
Fired when a request returns an error and the event bubbles up to the connection object. Also available via the `onerror` property.

[`versionchange`](idbdatabase/versionchange_event)  
Fired when a database structure change was requested. Also available via the `onversionchange` property.

Example
-------

In the following code snippet, we open a database asynchronously ([`IDBFactory`](idbfactory)), handle success and error cases, and create a new object store in the case that an upgrade is needed ([`IDBdatabase`](idbdatabase)). For a complete working example, see our [To-do Notifications](https://github.com/mdn/to-do-notifications/) app ([view example live](https://mdn.github.io/to-do-notifications/).)

    // Let us open our database
    var DBOpenRequest = window.indexedDB.open("toDoList", 4);

    // these two event handlers act on the IDBDatabase object,
    // when the database is opened successfully, or not
    DBOpenRequest.onerror = function(event) {
      note.innerHTML += '<li>Error loading database.</li>';
    };

    DBOpenRequest.onsuccess = function(event) {
      note.innerHTML += '<li>Database initialised.</li>';

      // store the result of opening the database in the db
      // variable. This is used a lot later on
      db = DBOpenRequest.result;

      // Run the displayData() function to populate the task
      // list with all the to-do list data already in the IDB
      displayData();
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

      // Create an objectStore for this database using
      // IDBDatabase.createObjectStore

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

This next line opens up a transaction on the Database, then opens an object store that we can then manipulate the data inside of.

    var objectStore = db.transaction('toDoList', 'readwrite').objectStore('toDoList');

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#idbdatabase">Indexed Database API 2.0<br />
<span class="small">The definition of 'IDBDatabase' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial version</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#database-interface">Indexed Database API 2.0<br />
<span class="small">The definition of 'IDBDatabase' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`IDBDatabase`

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

`abort_event`

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

`close`

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

`close_event`

31

≤18

50

?

Yes

10.1

≤37

31

50

Yes

10.3

2.0

`createObjectStore`

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

`deleteObjectStore`

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

`error_event`

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

`objectStoreNames`

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

`onabort`

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

`onclose`

31

approx

≤18

50

No

Yes

10.1

≤37

31

50

Yes

10.3

2.0

`onerror`

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

`onversionchange`

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

`version`

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

`versionchange_event`

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

23

≤18

37

?

Yes

?

≤37

25

37

Yes

?

1.5

See also
--------

-   [Using IndexedDB](indexeddb_api/using_indexeddb)
-   Starting transactions: [`IDBDatabase`](idbdatabase)
-   Using transactions: [`IDBTransaction`](idbtransaction)
-   Setting a range of keys: [`IDBKeyRange`](idbkeyrange)
-   Retrieving and making changes to your data: [`IDBObjectStore`](idbobjectstore)
-   Using cursors: [`IDBCursor`](idbcursor)
-   Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase</a>
