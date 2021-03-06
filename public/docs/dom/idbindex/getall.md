# IDBIndex.getAll()

The `getAll()` method of the [`IDBIndex`](../idbindex) interface retrieves all objects that are inside the index.

There is a performance cost associated with looking at the `value` property of a cursor, because the object is created lazily. To use a feature like `getAll()`, the browser has to create all the objects at once. If you are just interested in looking at each of the keys, for instance, it is more efficient to use a [cursor](../idbcursor). If you are trying to get an array of all the objects in an object store, though, you should use `getAll()`.

## Syntax

    var getAllKeysRequest = IDBIndex.getAll();
    var getAllKeysRequest = IDBIndex.getAll(query);
    var getAllKeysRequest = IDBIndex.getAll(query, count);

### Parameters

_query_ <span class="badge inline optional">Optional</span>  
A key or an [`IDBKeyRange`](../idbkeyrange) identifying the records to retrieve. If this value is null or missing, the browser will use an unbound key range.

_count_ <span class="badge inline optional">Optional</span>  
The number records to return. If this value exceeds the number of records in the query, the browser will only retrieve the first item. If it is lower than `0` or greater than `232-1` a [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError) exception will be thrown.

### Return value

An [`IDBRequest`](../idbrequest) object on which subsequent events related to this operation are fired.

### Exceptions

This method may raise a [`DOMException`](../domexception) of the following types:

<table><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>TransactionInactiveError</code></td><td>This <a href="../idbindex"><code>IDBIndex</code></a>'s transaction is inactive.</td></tr><tr class="even"><td><code>InvalidStateError</code></td><td>The <a href="../idbindex"><code>IDBIndex</code></a> has been deleted or removed.</td></tr></tbody></table>

A [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError) exception is thrown if the `count` parameter is not between `0` and `232-1` included.

## Example

    var myIndex = objectStore.index('index');
    var getAllRequest = myIndex.getAll();
    getAllRequest.onsuccess = function() {
      console.log(getAllRequest.result);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbindex-getall">Indexed Database API 2.0<br />
<span class="small">The definition of 'getAll()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getAll`

48

???18

44

No

35

10.1

48

48

44

35

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBIndex/getAll" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBIndex/getAll</a>
