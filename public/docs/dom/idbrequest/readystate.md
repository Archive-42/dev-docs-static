IDBRequest.readyState
=====================

The `readyState` read-only property of the [`IDBRequest`](../idbrequest) interface returns the state of the request.

<span style="line-height: 1.5;">Every request starts in the </span>`pending`<span style="line-height: 1.5;"> state. The state changes to </span>`done`<span style="line-height: 1.5;"> when the request completes successfully or when an error occurs.</span>

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var currentReadyState = request.readyState;

### Value

The <span class="page-not-created">`IDBRequestReadyState`</span> of the request, which takes one of the following two values:

<table><thead><tr class="header"><th>Value</th><th>Meaning</th></tr></thead><tbody><tr class="odd"><td><code>pending</code></td><td>The request is pending.</td></tr><tr class="even"><td><code>done</code></td><td>The request is done.<br />
</td></tr></tbody></table>

Example
-------

The following example requests a given record title, `onsuccess` gets the associated record from the [`IDBObjectStore`](../idbobjectstore) (made available as `objectStoreTitleRequest.result`<span style="line-height: 1.5;">), updates one property of the record, and then puts the updated record back into the object store in another request. The `readyState` of the 2nd request is logged to the developer console. For a full working example, see our </span>[To-do Notifications](https://github.com/mdn/to-do-notifications/)<span style="line-height: 1.5;"> app (</span>[view example live](https://mdn.github.io/to-do-notifications/)<span style="line-height: 1.5;">.)</span>

    var title = "Walk dog";

    // Open up a transaction as usual
    var objectStore = db.transaction(['toDoList'], "readwrite").objectStore('toDoList');

    // Get the to-do list object that has this title as it's title
    var objectStoreTitleRequest = objectStore.get(title);

    objectStoreTitleRequest.onsuccess = function() {
      // Grab the data object returned as the result
      var data = objectStoreTitleRequest.result;

      // Update the notified value in the object to "yes"
      data.notified = "yes";

      // Create another request that inserts the item
      // back into the database
      var updateTitleRequest = objectStore.put(data);

      // Log the source of this request
      console.log("The readyState of this request is " + updateTitlerequest.readyState);

      // When this new request succeeds, run the displayData()
      // function again to update the display
      updateTitleRequest.onsuccess = function() {
        displayData();
      };
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbrequest-readystate">Indexed Database API 2.0<br />
<span class="small">The definition of 'readyState' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbrequest-readystate">Indexed Database API 2.0<br />
<span class="small">The definition of 'readyState' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

See also
--------

-   [Using IndexedDB](../indexeddb_api/using_indexeddb)
-   Starting transactions: [`IDBDatabase`](../idbdatabase)
-   Using transactions: [`IDBTransaction`](../idbtransaction)
-   Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
-   Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
-   Using cursors: [`IDBCursor`](../idbcursor)
-   Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBRequest/readyState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBRequest/readyState</a>
