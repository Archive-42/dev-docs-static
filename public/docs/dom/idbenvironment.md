IDBEnvironment
==============

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Important**: The `indexedDB` property that was previously defined in this mixin is instead now [`WindowOrWorkerGlobalScope.indexedDB`](windoworworkerglobalscope/indexeddb) (that is, defined as a member of the [`WindowOrWorkerGlobalScope`](windoworworkerglobalscope) mixin).

The `IDBEnvironment` helper of the [IndexedDB API](indexeddb_api) contains the `indexedDB` property, which provides access to IndexedDB functionality. It is the top level IndexedDB interface implemented by the [`window`](window) and [`Worker`](worker) objects.

**Note:** This feature is available in [Web Workers](web_workers_api).

Properties
----------

 [`WindowOrWorkerGlobalScope.indexedDB`](windoworworkerglobalscope/indexeddb) <span class="badge inline readonly">Read only </span>   
Provides a mechanism for applications to asynchronously access capabilities of indexed databases; contains an [`IDBFactory`](idbfactory) object.

Example
-------

The following code creates a request for a database to be opened asynchronously, after which the database is opened when the request's `onsuccess` handler is fired:

    var db;
    function openDB() {
     var DBOpenRequest = window.indexedDB.open("toDoList");
     DBOpenRequest.onsuccess = function(e) {
       db = DBOpenRequest.result;
     };
    }

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

`IDBEnvironment`

24

23-57

12

16

10-16

10

15

7

Yes

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBEnvironment" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBEnvironment</a>
