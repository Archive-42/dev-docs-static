# IDBFactory.deleteDatabase()

The `deleteDatabase()` method of the [`IDBFactory`](../idbfactory) interface requests the deletion of a database. The method returns an [`IDBOpenDBRequest`](../idbopendbrequest) object immediately, and performs the deletion operation asynchronously.

If the database is successfully deleted, then a `success` event is fired on the request object returned from this method, with its `result` set to `undefined`. If an error occurs while the database is being deleted, then an `error` event is fired on the request object that is returned from this method.

When `deleteDatabase()` is called, any other open connections to this particular database will get a [versionchange](../idbdatabase/versionchange_event) event.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

For the current standard:

    var request = indexedDB.deleteDatabase(name);

<span class="idlInterface"><span class="idlMethod">For the experimental version with `options` (see below):</span></span>

    var request = indexedDB.deleteDatabase(name, options);

### Parameters

name  
The name of the database you want to delete. Note that attempting to delete a database that doesn't exist does not throw an exception, in contrast to [`IDBDatabase.deleteObjectStore()`](../idbdatabase/deleteobjectstore), which does throw an exception if the named object store does not exist.

options<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
In Gecko, since [version 26](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Releases/26), you can include a non-standard optional storage parameter that specifies whether you want to delete a `permanent` (the default value) IndexedDB, or an indexedDB in `temporary` storage (aka shared pool.)

### Return value

A [`IDBOpenDBRequest`](../idbopendbrequest) on which subsequent events related to this request are fired.

## Example

    var DBDeleteRequest = window.indexedDB.deleteDatabase("toDoList");

    DBDeleteRequest.onerror = function(event) {
      console.log("Error deleting database.");
    };

    DBDeleteRequest.onsuccess = function(event) {
      console.log("Database deleted successfully");

      console.log(event.result); // should be undefined
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbfactory-deletedatabase">Indexed Database API 2.0<br />
<span class="small">The definition of 'deleteDatabase()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbfactory-deletedatabase">Indexed Database API 2.0<br />
<span class="small">The definition of 'deleteDatabase()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`deleteDatabase`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBFactory/deleteDatabase" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBFactory/deleteDatabase</a>
