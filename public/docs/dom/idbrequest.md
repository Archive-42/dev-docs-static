IDBRequest
==========

The `IDBRequest` interface of the IndexedDB API provides access to results of asynchronous requests to databases and database objects using event handler attributes. Each reading and writing operation on a database is done using a request.

The request object does not initially contain any information about the result of the operation, but once information becomes available, an event is fired on the request, and the information becomes available through the properties of the `IDBRequest` instance.

All asynchronous operations immediately return an [`IDBRequest`](idbrequest) instance. Each request has a `readyState` that is set to the `'pending'` state; this changes to `'done'` when the request is completed or fails. When the state is set to `done`, every request returns a `result` and an `error`, and an event is fired on the request. When the state is still `pending`, any attempt to access the `result` or `error` raises an `InvalidStateError` exception.

In plain words, all asynchronous methods return a request object. If the request has been completed successfully, the result is made available through the `result` property and an event indicating success is fired at the request ([`IDBRequest.onsuccess`](idbrequest/onsuccess)). If an error occurs while performing the operation, the exception is made available through the `result` property and an error event is fired ([`IDBRequest.onerror`](idbrequest/onerror)).

The interface [`IDBOpenDBRequest`](idbopendbrequest) is derived from `IDBRequest`.

**Note:** This feature is available in [Web Workers](web_workers_api).

Properties
----------

*Also inherits properties from [`EventTarget`](eventtarget).*

 [`IDBRequest.error`](idbrequest/error) <span class="badge inline readonly">Read only </span>   
Returns a [`DOMException`](domexception) in the event of an unsuccessful request, indicating what went wrong.

 [`IDBRequest.result`](idbrequest/result) <span class="badge inline readonly">Read only </span>   
Returns the result of the request. If the request failed and the result is not available, an InvalidStateError exception is thrown.

 [`IDBRequest.source`](idbrequest/source) <span class="badge inline readonly">Read only </span>   
The source of the request, such as an [`IDBIndex`](idbindex) or an [`IDBObjectStore`](idbobjectstore). If no source exists (such as when calling [`IDBFactory.open`](idbfactory/open)), it returns null.

 [`IDBRequest.readyState`](idbrequest/readystate) <span class="badge inline readonly">Read only </span>   
The state of the request. Every request starts in the `pending` state. The state changes to `done` when the request completes successfully or when an error occurs.

 [`IDBRequest.transaction`](idbrequest/transaction) <span class="badge inline readonly">Read only </span>   
The transaction for the request. This property can be null for certain requests, for example those returned from [`IDBFactory.open`](idbfactory/open) unless an upgrade is needed. (You're just connecting to a database, so there is no transaction to return).

Methods
-------

*No methods, but inherits methods from [`EventTarget`](eventtarget).*

Events
------

Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

[`error`](idbrequest/error_event)  
Fired when an error caused a request to fail.  
Also available via the `onerror` property.

[`success`](idbrequest/success_event)  
Fired when an `IDBRequest` succeeds.  
Also available via the `onsuccess` property.

Example
-------

In the following code snippet, we open a database asynchronously and make a request; `onerror` and `onsuccess` functions are included to handle the success and error cases. For a full working example, see our [To-do Notifications](https://github.com/chrisdavidmills/to-do-notifications/tree/gh-pages) app ([view example live](https://chrisdavidmills.github.io/to-do-notifications/).)

    var db;

    // Let us open our database
    var DBOpenRequest = window.indexedDB.open("toDoList", 4);

    // these two event handlers act on the database being
    // opened successfully, or not
    DBOpenRequest.onerror = function(event) {
      note.innerHTML += '<li>Error loading database.</li>';
    };

    DBOpenRequest.onsuccess = function(event) {
      note.innerHTML += '<li>Database initialised.</li>';

      // store the result of opening the database.
      db = DBOpenRequest.result;
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#idbrequest">Indexed Database API 2.0<br />
<span class="small">The definition of 'IDBRequest' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#request-api">Indexed Database API 2.0<br />
<span class="small">The definition of 'IDBRequest' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`IDBRequest`

24

2-57

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

`error`

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

Yes

Yes

22

14

8

Yes

`onerror`

23

12

10

10

15

7

≤37

Yes

22

14

8

Yes

`onsuccess`

23

12

10

10

15

7

≤37

Yes

22

14

8

Yes

`readyState`

23

12

10

10

15

7

≤37

Yes

22

14

8

Yes

`result`

23

12

10

10

15

7

≤37

Yes

22

14

8

Yes

`source`

23

12

10

10

15

7

≤37

Yes

22

14

8

Yes

`success_event`

23

12

10

10

15

7

Yes

Yes

22

14

8

Yes

`transaction`

23

12

10

10

15

7

≤37

Yes

22

14

8

Yes

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBRequest" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBRequest</a>
