IDBOpenDBRequest.onupgradeneeded
================================

The `onupgradeneeded` property of the [`IDBOpenDBRequest`](../idbopendbrequest) interface is the event handler for the `upgradeneeded` event, triggered when a database of a bigger version number than the existing stored database is loaded.

The event passed to the handler is an [`IDBVersionChangeEvent`](../idbversionchangeevent).

Inside the event handler function you can include code to upgrade the database structure, as shown in the example below.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    IDBOpenDBRequest.onupgradeneeded = function(event) { ... };

Example
-------

In the following example you can see the onupgradeneeded handler being used to update the database structure if a database with a higher version number is loaded. For a full working example, see our [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) app ([view example live](https://mdn.github.io/to-do-notifications/).)

    var db;

    // Request version 3 of the database.
    var request = window.indexedDB.open("library", 3);

    // This event handles the event whereby a new version of the
    // database needs to be created. Either one has not been created
    // before, or a new version number has been submitted via the
    // window.indexedDB.open line above.
    request.onupgradeneeded = function(event) {
      db = request.result;

      db.onerror = function(errorEvent) {
        note.innerHTML += '<li>Error loading database.</li>';
      };

      if (event.oldVersion < 1) {
        // Version 1 is the first version of the database.
        var store = db.createObjectStore("books", {keyPath: "isbn"});
        var titleIndex = store.createIndex("by_title", "title", {unique: true});
        var authorIndex = store.createIndex("by_author", "author");
      }
      if (event.oldVersion < 2) {
        // Version 2 introduces a new index of books by year.
        var bookStore = request.transaction.objectStore("books");
        var yearIndex = bookStore.createIndex("by_year", "year");
      }
      if (event.oldVersion < 3) {
        // Version 3 introduces a new object store for magazines with two indexes.
        var magazines = db.createObjectStore("magazines");
        var publisherIndex = magazines.createIndex("by_publisher", "publisher");
        var frequencyIndex = magazines.createIndex("by_frequency", "frequency");
      }
    };

    request.onerror = function(event) {
      note.innerHTML += '<li>Error loading database.</li>';
    };

    request.onsuccess = function(event) {
      note.innerHTML += '<li>Database initialised.</li>';
      db = request.result;
      populateAndDisplayData();
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbopendbrequest-onupgradeneeded">Indexed Database API 2.0<br />
<span class="small">The definition of 'onupgradeneeded' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbopendbrequest-onupgradeneeded">Indexed Database API 2.0<br />
<span class="small">The definition of 'onupgradeneeded' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

See also
--------

-   [Using IndexedDB](../indexeddb_api/using_indexeddb)
-   Starting transactions: [`IDBDatabase`](../idbdatabase)
-   Using transactions: [`IDBTransaction`](../idbtransaction)
-   Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
-   Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
-   Using cursors: [`IDBCursor`](../idbcursor)
-   Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)
-   `upgradeneeded` event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBOpenDBRequest/onupgradeneeded" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBOpenDBRequest/onupgradeneeded</a>
