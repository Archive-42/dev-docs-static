# IDBRequest.error

The `error` read-only property of the [`IDBRequest`](../idbrequest) interface returns the error in the event of an unsuccessful request.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    var myError = request.error;

### Value

A [`DOMError`](../domerror) containing the relevant error. In Chrome 48+/Firefox 58+ this property returns a [`DOMException`](../domexception) because `DOMError` has been removed from the DOM standard. The following error codes are returned under certain conditions:

<table><thead><tr class="header"><th>Error</th><th>Explanation</th></tr></thead><tbody><tr class="odd"><td><code>AbortError</code></td><td>If you abort the transaction, then all requests still in progress receive this error.</td></tr><tr class="even"><td><code>ConstraintError</code></td><td>If you insert data that doesn't conform to a constraint. It's an exception type for creating stores and indexes. You get this error, for example, if you try to add a new key that already exists in the record.</td></tr><tr class="odd"><td><code>QuotaExceededError</code></td><td>If you run out of disk quota and the user declined to grant you more space.</td></tr><tr class="even"><td><code>UnknownError</code></td><td>If the operation failed for reasons unrelated to the database itself. A failure due to disk IO errors is such an example.</td></tr><tr class="odd"><td><code>NoError</code></td><td>If the request succeeds.</td></tr><tr class="even"><td><code>VersionError</code></td><td>If you try to open a database with a version lower than the one it already has.</td></tr></tbody></table>

In addition to the error codes sent to the [`IDBRequest`](../idbrequest) object, asynchronous operations can also raise exceptions. The list describes problems that could occur when the request is being executed, but you might also encounter other problems when the request is being made. For example, if the request failed and the result is not available, the InvalidStateError exception is thrown.

## Example

The following example requests a given record title, `onsuccess` gets the associated record from the [`IDBObjectStore`](../idbobjectstore) (made available as `objectStoreTitleRequest.result`<span style="line-height: 1.5;">), updates one property of the record, and then puts the updated record back into the object store. Also included at the bottom is an `onerror` function that reports what the error was if the request fails. For a full working example, see our </span>[To-do Notifications](https://github.com/mdn/to-do-notifications/)<span style="line-height: 1.5;"> app (</span>[view example live](https://mdn.github.io/to-do-notifications/)<span style="line-height: 1.5;">.)</span>

    var title = "Walk dog";

    // Open up a transaction as usual
    var objectStore = db.transaction(['toDoList'], "readwrite").objectStore('toDoList');

    // Get the do-do list with the specified title
    var objectStoreTitleRequest = objectStore.get(title);

    objectStoreTitleRequest.onsuccess = function() {
      // Grab the data object returned as the result
      var data = objectStoreTitleRequest.result;

      // Update the notified value in the object to "yes"
      data.notified = "yes";

      // Create another request that inserts the item
      // back into the database
      var updateTitleRequest = objectStore.put(data);

      // When this new request succeeds, run the displayData()
      // function again to update the display
      updateTitleRequest.onsuccess = function() {
        displayData();
      };
    };

    objectStoreTitleRequest.onerror = function() {
      // If an error occurs with the request, log what it is
      console.log("There has been an error with retrieving your data: " + objectStoreTitleRequest.error);
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbrequest-error">Indexed Database API 2.0<br />
<span class="small">The definition of 'error' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbrequest-error">Indexed Database API 2.0<br />
<span class="small">The definition of 'error' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`DOMException`

48

≤18

58

No

Yes

No

48

48

58

Yes

No

5.0

## See also

- [Using IndexedDB](../indexeddb_api/using_indexeddb)
- Starting transactions: [`IDBDatabase`](../idbdatabase)
- Using transactions: [`IDBTransaction`](../idbtransaction)
- Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
- Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
- Using cursors: [`IDBCursor`](../idbcursor)
- Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBRequest/error" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBRequest/error</a>
