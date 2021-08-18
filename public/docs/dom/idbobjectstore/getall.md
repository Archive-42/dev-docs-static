# IDBObjectStore.getAll()

The `getAll()` method of the [`IDBObjectStore`](../idbobjectstore) interface returns an [`IDBRequest`](../idbrequest) object containing all objects in the object store matching the specified parameter or all objects in the store if no parameters are given.

If a value is successfully found, then a structured clone of it is created and set as the result of the request object.

This method produces the same result for:

- a record that doesn't exist in the database
- a record that has an undefined value

To tell these situations apart, you either call

1.  the [`openCursor()`](opencursor) method with the same key. That method provides a cursor if the record exists, and no cursor if it does not.
2.  the [`count()`](count) method with the same key, which will return 1 if the row exists and 0 if it doesn't.

## Syntax

    var request = objectStore.getAll();
    var request = objectStore.getAll(query);
    var request = objectStore.getAll(query, count);

### Parameters

_query_ <span class="badge inline optional">Optional</span>  
A key or [`IDBKeyRange`](../idbkeyrange) to be queried. If nothing is passed, this will default to a key range that selects all the records in this object store.

_count_ <span class="badge inline optional">Optional</span>  
Specifies the number of values to return if more than one is found. If it is lower than `0` or greater than `232-1` a [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError) exception will be thrown.

### Return value

An [`IDBRequest`](../idbrequest) object on which subsequent events related to this operation are fired.

### Exceptions

This method may raise a [`DOMException`](../domexception) of one of the following types:

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>TransactionInactiveError</code></td><td>This <a href="../idbobjectstore"><code>IDBObjectStore</code></a>'s transaction is inactive.</td></tr><tr class="even"><td><code>DataError</code></td><td><p>The key or key range provided contains an invalid key or is null.</p></td></tr><tr class="odd"><td><code>InvalidStateError</code></td><td>The <a href="../idbobjectstore"><code>IDBObjectStore</code></a> has been deleted or removed.<br />
</td></tr></tbody></table>

A [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError) exception is thrown if the `count` parameter is not between `0` and `232-1` included.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbobjectstore-getall">Indexed Database API 2.0<br />
<span class="small">The definition of 'getAll()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

≤79

44

No

35

10.1

48

48

48

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/getAll" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/getAll</a>
