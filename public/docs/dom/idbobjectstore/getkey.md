# IDBObjectStore.getKey()

The `getKey()` method of the [`IDBObjectStore`](../idbobjectstore) interface returns an [`IDBRequest`](../idbrequest) object, and, in a separate thread, returns the key selected by the specified query. This is for retrieving specific records from an object store.

If a key is successfully found, then a structured clone of it is created and set as the result of the request object.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    var request = objectStore.getKey(key);

### Parameters

_key_  
The key or key range that identifies the record to be retrieved.

### Return Value

An [`IDBRequest`](../idbrequest) object on which subsequent events related to this operation are fired.

### Exceptions

This method may raise a [`DOMException`](../domexception) of one of the following types:

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>TransactionInactiveError</code></td><td>This <a href="../idbobjectstore"><code>IDBObjectStore</code></a>'s transaction is inactive.</td></tr><tr class="even"><td><code>DataError</code></td><td><p>The key or key range provided contains an invalid key.</p></td></tr><tr class="odd"><td><code>InvalidStateError</code></td><td>The <a href="../idbobjectstore"><code>IDBObjectStore</code></a> has been deleted or removed.<br />
</td></tr></tbody></table>

## Example

    let openRequest = indexedDB.open("telemetry");
    openRequest.onsuccess = (event) => {
      let db = event.target.result;
      let store = db.transaction("netlogs").objectStore("netlogs");

      let today = new Date();
      let yesterday = new Date(today);
      yesterday.setDate(today.getDate() - 1);
      let request = store.getKey(IDBKeyRange(yesterday, today));
      request.onsuccess = (event) => {
        let when = event.target.result;
        alert("The 1st activity in last 24 hours was occurred at " + when);
      };
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbobjectstore-getkey">Indexed Database API 2.0<br />
<span class="small">The definition of 'getKey()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

## See also

- [Using IndexedDB](../indexeddb_api/using_indexeddb)
- Starting transactions: [`IDBDatabase`](../idbdatabase)
- Using transactions: [`IDBTransaction`](../idbtransaction)
- Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
- Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
- Using cursors: [`IDBCursor`](../idbcursor)
- Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/getKey" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/getKey</a>
