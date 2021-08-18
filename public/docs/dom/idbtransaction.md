IDBTransaction
==============

The `IDBTransaction` interface of the [IndexedDB API](indexeddb_api) provides a static, asynchronous transaction on a database using event handler attributes. All reading and writing of data is done within transactions. You use [`IDBDatabase`](idbdatabase) to start transactions, [`IDBTransaction`](idbtransaction) to set the mode of the transaction (e.g. is it `readonly` or `readwrite`), and you access an [`IDBObjectStore`](idbobjectstore) to make a request. You can also use an `IDBTransaction` object to abort transactions.

**Note:** This feature is available in [Web Workers](web_workers_api).

Transactions are started when the transaction is created, not when the first request is placed; for example consider this:

    var trans1 = db.transaction("foo", "readwrite");
    var trans2 = db.transaction("foo", "readwrite");
    var objectStore2 = trans2.objectStore("foo")
    var objectStore1 = trans1.objectStore("foo")
    objectStore2.put("2", "key");
    objectStore1.put("1", "key");

After the code is executed the object store should contain the value "2", since `trans2` should run after `trans1`.

Transaction failures
--------------------

Transactions can fail for a fixed number of reasons, all of which (except the user agent crash) will trigger an abort callback:

-   Abort due to bad requests, e.g. trying to `add()` the same key twice, or `put()` with the same index key with a uniqueness constraint. This causes an error on the request, which can bubble up to an error on the transaction, which aborts the transaction. This can be prevented by using `preventDefault()` on the error event on the request.
-   An explicit `abort()` call from script.
-   An uncaught exception in the request's `success`/`error` handler.
-   An I/O error (e.g. an actual failure to write to disk, or other OS/hardware failure).
-   Quota exceeded.
-   A user agent crash.

Firefox durability guarantees
-----------------------------

Note that as of Firefox 40, IndexedDB transactions have relaxed durability guarantees to increase performance (see [bug 1112702](https://bugzilla.mozilla.org/show_bug.cgi?id=1112702).) Previously in a `readwrite` transaction [`IDBTransaction.oncomplete`](idbtransaction/oncomplete) was fired only when all data was guaranteed to have been flushed to disk. In Firefox 40+ the `complete` event is fired after the OS has been told to write the data but potentially before that data has actually been flushed to disk. The `complete` event may thus be delivered quicker than before, however, there exists a small chance that the entire transaction will be lost if the OS crashes or there is a loss of system power before the data is flushed to disk. Since such catastrophic events are rare, most consumers should not need to concern themselves further.

If you must ensure durability for some reason (e.g. you're storing critical data that cannot be recomputed later) you can force a transaction to flush to disk before delivering the `complete` event by creating a transaction using the experimental (non-standard) `readwriteflush` mode (see [`IDBDatabase.transaction`](idbdatabase/transaction).

Properties
----------

 [`IDBTransaction.db`](idbtransaction/db) <span class="badge inline readonly">Read only </span>   
The database connection with which this transaction is associated.

 [`IDBTransaction.durability`](idbtransaction/durability) <span class="badge inline readonly">Read only </span>   
Returns the durability hint the transaction was created with.

 [`IDBTransaction.error`](idbtransaction/error) <span class="badge inline readonly">Read only </span>   
Returns a [`DOMException`](domexception) indicating the type of error that occurred when there is an unsuccessful transaction. This property is `null` if the transaction is not finished, is finished and successfully committed, or was aborted with the[`IDBTransaction.abort()`](idbtransaction/abort) function.

 [`IDBTransaction.mode`](idbtransaction/mode) <span class="badge inline readonly">Read only </span>   
The mode for isolating access to data in the object stores that are in the scope of the transaction. The default value is `readonly`.

 [`IDBTransaction.objectStoreNames`](idbtransaction/objectstorenames) <span class="badge inline readonly">Read only </span>   
Returns a [`DOMStringList`](domstringlist) of the names of [`IDBObjectStore`](idbobjectstore) objects associated with the transaction.

Methods
-------

Inherits from: [`EventTarget`](eventtarget)

[`IDBTransaction.abort()`](idbtransaction/abort)  
Rolls back all the changes to objects in the database associated with this transaction. If this transaction has been aborted or completed, this method fires an error event.

[`IDBTransaction.objectStore()`](idbtransaction/objectstore)  
Returns an [`IDBObjectStore`](idbobjectstore) object representing an <span class="internalDFN">object store</span> that is part of the <span class="internalDFN">scope</span> of this <span class="internalDFN">transaction</span>.

[`IDBTransaction.commit()`](idbtransaction/commit)  
For an active transaction, commits the transaction. Note that this doesn't normally *have* to be called — a transaction will automatically commit when all outstanding requests have been satisfied and no new requests have been made. `commit()` can be used to start the commit process without waiting for events from outstanding requests to be dispatched.

Events
------

Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

[`abort`](idbtransaction/abort_event)  
Fired when an `IndexedDB` transaction is aborted.  
Also available via the `onabort` property.

[`complete`](idbtransaction/complete_event)  
Fired when a transaction successfully completes.  
Also available via the `oncomplete` property.

[`error`](idbtransaction/error_event)  
Fired when a request returns an error and the event bubbles up to the transaction object.  
Also available via the `onerror` property.

Mode constants
--------------

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

These constants are no longer available — they were removed in Gecko 25. You should use the string constants directly instead. ([bug 888598](https://bugzilla.mozilla.org/show_bug.cgi?id=888598))

Transactions can have one of three modes:

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Constant</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>READ_ONLY</code></td><td><p>"readonly"</p><p>(0 in Chrome)</p></td><td><p>Allows data to be read but not changed.</p></td></tr><tr class="even"><td><code>READ_WRITE</code></td><td><p>"readwrite"</p><p>(1 in Chrome)</p></td><td>Allows reading and writing of data in existing data stores to be changed.</td></tr><tr class="odd"><td><code>VERSION_CHANGE</code></td><td><p>"versionchange"</p><p>(2 in Chrome)</p></td><td>Allows any operation to be performed, including ones that delete and create object stores and indexes. This mode is for updating the version number of transactions that were started using the <a href="idbdatabase#setversion"><code>setVersion()</code></a> method of <a href="idbdatabase">IDBDatabase</a> objects. Transactions of this mode cannot run concurrently with other transactions. Transactions in this mode are known as "upgrade transactions."</td></tr></tbody></table>

Even if these constants are now deprecated, you can still use them to provide backward compatibility if required (in Chrome [the change was made in version 21](https://peter.sh/2012/05/tab-sizing-string-values-for-indexeddb-and-chrome-21/)). You should code defensively in case the object is not available anymore:

    var myIDBTransaction = window.IDBTransaction || window.webkitIDBTransaction || { READ_WRITE: "readwrite" };

Examples
--------

In the following code snippet, we open a read/write transaction on our database and add some data to an object store. Note also the functions attached to transaction event handlers to report on the outcome of the transaction opening in the event of success or failure. For a full working example, see our [To-do Notifications](https://github.com/mdn/to-do-notifications/) app ([view example live](https://mdn.github.io/to-do-notifications/).)

    // Let us open our database
    var DBOpenRequest = window.indexedDB.open("toDoList", 4);

    DBOpenRequest.onsuccess = function(event) {
      note.innerHTML += '<li>Database initialised.</li>';

      // store the result of opening the database in the db
      // variable. This is used a lot below
      db = DBOpenRequest.result;

      // Add the data to the database
      addData();
    };

    function addData() {
      // Create a new object to insert into the IDB
      var newItem = [ { taskTitle: "Walk dog", hours: 19, minutes: 30, day: 24, month: "December", year: 2013, notified: "no" } ];

      // open a read/write db transaction, ready to add data
      var transaction = db.transaction(["toDoList"], "readwrite");

      // report on the success of opening the transaction
      transaction.oncomplete = function(event) {
        note.innerHTML += '<li>Transaction completed: database modification finished.</li>';
      };

      transaction.onerror = function(event) {
      note.innerHTML += '<li>Transaction not opened due to error. Duplicate items not allowed.</li>';
      };

      // create an object store on the transaction
      var objectStore = transaction.objectStore("toDoList");

      // add our newItem object to the object store
      var objectStoreRequest = objectStore.add(newItem[0]);

      objectStoreRequest.onsuccess = function(event) {
        // report the success of the request (this does not mean the item
        // has been stored successfully in the DB - for that you need transaction.oncomplete)
        note.innerHTML += '<li>Request successful.</li>';
      };
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#transaction">Indexed Database API 2.0<br />
<span class="small">The definition of 'IDBTransaction' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#transaction">Indexed Database API 2.0<br />
<span class="small">The definition of 'IDBTransaction' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`IDBTransaction`

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

`abort`

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

`abort_event`

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

`commit`

76

79

74

No

63

No

76

76

No

54

No

12.0

`complete_event`

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

`db`

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

`durability`

83

83

No

No

70

No

83

83

No

59

No

13.0

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

`mode`

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

`objectStore`

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

`objectStoreNames`

48

≤79

Yes

No

35

Yes

48

48

Yes

35

Yes

5.0

`onabort`

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

`oncomplete`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBTransaction" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBTransaction</a>
