WindowOrWorkerGlobalScope.indexedDB
===================================

The `indexedDB` read-only property of the [`WindowOrWorkerGlobalScope`](../windoworworkerglobalscope) mixin provides a mechanism for applications to asynchronously access the capabilities of indexed databases.

Syntax
------

    var IDBFactory = self.indexedDB;

### Value

An [`IDBFactory`](../idbfactory) object.

Example
-------

The following code creates a request for a database to be opened asynchronously, after which the database is opened when the request's `onsuccess` handler is fired:

    var db;
    function openDB() {
     var DBOpenRequest = window.indexedDB.open('toDoList');
     DBOpenRequest.onsuccess = function(e) {
       db = DBOpenRequest.result;
     }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-windoworworkerglobalscope-indexeddb">Indexed Database API 2.0<br />
<span class="small">The definition of 'indexedDB' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Defined in a <code>WindowOrWorkerGlobalScope</code> partial in the newest spec.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-windoworworkerglobalscope-indexeddb">Indexed Database API 2.0<br />
<span class="small">The definition of 'indexedDB' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`indexedDB`

24

12

16

10

10

15

7

≤37

25

22

14

8

2.0

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

-   [Using IndexedDB](../indexeddb_api/using_indexeddb)
-   Starting transactions: [`IDBDatabase`](../idbdatabase)
-   Using transactions: [`IDBTransaction`](../idbtransaction)
-   Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
-   Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
-   Using cursors: [`IDBCursor`](../idbcursor)
-   Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/indexedDB" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/indexedDB</a>
