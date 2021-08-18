# IDBDatabase.deleteObjectStore()

The `deleteObjectStore()` method of the [`IDBDatabase`](../idbdatabase) interface destroys the object store with the given name in the connected database, along with any indexes that reference it.

As with [`IDBDatabase.createObjectStore`](createobjectstore), this method can be called _only_ within a [`versionchange`](../idbtransaction#version_change) transaction.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    dbInstance.deleteObjectStore(name);

### Parameters

`name`  
The name of the object store you want to delete.

### Exceptions

This method may raise a [`DOMException`](../domexception) of one of the following types:

<table><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>InvalidStateError</code></td><td>Occurs if the method was not called from a <code>versionchange</code> transaction callback. For older WebKit browsers, you must call first.</td></tr><tr class="even"><td><code>TransactionInactiveError</code></td><td>Occurs if a request is made on a source database that doesn't exist (e.g. has been deleted or removed.) In Firefox previous to version 41, an <code>InvalidStateError</code> was raised in this case as well, which was misleading; this has now been fixed (see <a href="https://bugzilla.mozilla.org/show_bug.cgi?id=1176165">bug 1176165</a>.)</td></tr><tr class="odd"><td><code>NotFoundError</code></td><td>You are trying to delete an object store that does not exist. Names are case sensitive.</td></tr></tbody></table>

## Example

    var dbName = "sampleDB";
    var dbVersion = 2;
    var request = indexedDB.open(dbName, dbVersion);

    request.onupgradeneeded = function(e) {
      var db = request.result;
      if (e.oldVersion < 1) {
        db.createObjectStore("store1");
      }

      if (e.oldVersion < 2) {
        db.deleteObjectStore("store1");
        db.createObjectStore("store2");
      }

      // etc. for version < 3, 4...
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbdatabase-deleteobjectstore">Indexed Database API 2.0<br />
<span class="small">The definition of 'deleteObjectStore()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbdatabase-deleteobjectstore">Indexed Database API 2.0<br />
<span class="small">The definition of 'deleteObjectStore()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`deleteObjectStore`

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

## See also

- [Using IndexedDB](../indexeddb_api/using_indexeddb)
- Starting transactions: [`IDBDatabase`](../idbdatabase)
- Using transactions: [`IDBTransaction`](../idbtransaction)
- Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
- Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
- Using cursors: [`IDBCursor`](../idbcursor)
- Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/deleteObjectStore" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/deleteObjectStore</a>
