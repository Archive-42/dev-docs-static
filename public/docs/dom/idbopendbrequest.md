IDBOpenDBRequest
================

The `IDBOpenDBRequest` interface of the IndexedDB API provides access to the results of requests to open or delete databases (performed using [`IDBFactory.open`](idbfactory/open) and [`IDBFactory.deleteDatabase`](idbfactory/deletedatabase)), using specific event handler attributes.

**Note:** This feature is available in [Web Workers](web_workers_api).

Properties
----------

*Also inherits methods from its parents [`IDBRequest`](idbrequest) and [`EventTarget`](eventtarget)*.

Methods
-------

*No methods, but inherits methods from its parents [`IDBRequest`](idbrequest) and [`EventTarget`](eventtarget).*

Events
------

Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

[`blocked`](idbopendbrequest/blocked_event)  
Fired when an open connection to a database is blocking a `versionchange` transaction on the same database. Also available via the `onblocked` property.

[`upgradeneeded`](idbopendbrequest/upgradeneeded_event)  
Fired when an attempt was made to open a database with a version number higher than its current version. Also available via the `onupgradeneeded` property.

Example
-------

In the following example you can see the onupgradeneeded handler being used to update the database structure if a database with a higher version number is loaded. For a full working example, see our [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) app ([view example live](https://mdn.github.io/to-do-notifications/).)

    var db;

    // Let us open our database
    var DBOpenRequest = window.indexedDB.open("toDoList", 4);

    // these event handlers act on the database being opened.
    DBOpenRequest.onerror = function(event) {
      note.innerHTML += '<li>Error loading database.</li>';
    };

    DBOpenRequest.onsuccess = function(event) {
      note.innerHTML += '<li>Database initialised.</li>';

      // store the result of opening the database in the db
      // variable. This is used a lot below
      db = DBOpenRequest.result;

      // Run the displayData() function to populate the task
      // listwith all the to-do list data already in the IDB
      displayData();
    };

    // This event handles the event whereby a new version of
    // the database needs to be created Either one has not
    // been created before, or a new version number has been
    // submitted via the window.indexedDB.open line above
    // it is only implemented in recent browsers
    DBOpenRequest.onupgradeneeded = function(event) {
      var db = this.result;

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
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#idbopendbrequest">Indexed Database API 2.0<br />
<span class="small">The definition of 'IDBOpenDBRequest' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#idbopendbrequest">Indexed Database API 2.0<br />
<span class="small">The definition of 'IDBOpenDBRequest' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`IDBOpenDBRequest`

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

`blocked_event`

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

`onupgradeneeded`

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

`upgradeneeded_event`

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

See also
--------

-   [Using IndexedDB](indexeddb_api/using_indexeddb)
-   Starting transactions: [`IDBDatabase`](idbdatabase)
-   Using transactions: [`IDBTransaction`](idbtransaction)
-   Setting a range of keys: [`IDBKeyRange`](idbkeyrange)
-   Retrieving and making changes to your data: [`IDBObjectStore`](idbobjectstore)
-   Using cursors: [`IDBCursor`](idbcursor)
-   Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBOpenDBRequest" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBOpenDBRequest</a>
