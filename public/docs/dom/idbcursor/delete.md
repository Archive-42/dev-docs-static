# IDBCursor.delete()

The `delete()` method of the [`IDBCursor`](../idbcursor) interface returns an [`IDBRequest`](../idbrequest) object, and, in a separate thread, deletes the record at the cursor's position, without changing the cursor's position. Once the record is deleted, the cursor's value is set to null.

Be aware that you can't call `delete()` (or [`IDBCursor.update()`](update)) on cursors obtained from [`IDBIndex.openKeyCursor()`](../idbindex/openkeycursor). For such needs, you have to use [`IDBIndex.openCursor()`](../idbindex/opencursor) instead.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    myIDBCursor.delete();

### Returns

An [`IDBRequest`](../idbrequest) object on which subsequent events related to this operation are fired. The result attribute is set to undefined.

### Exceptions

This method may raise a [`DOMException`](../domexception) of one of the following types:

<table><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>TransactionInactiveError</code></td><td>This IDBCursor's transaction is inactive.</td></tr><tr class="even"><td><code>ReadOnlyError</code></td><td>The transaction mode is read-only.</td></tr><tr class="odd"><td><code>InvalidStateError</code></td><td>The cursor was created using <a href="../idbindex/openkeycursor"><code>IDBindex.openKeyCursor</code></a>, is currently being iterated, or has iterated past its end.</td></tr></tbody></table>

## Example

In this simple fragment we create a transaction, retrieve an object store, then use a cursor to iterate through all the records in the object store. If the `albumTitle` of the current cursor is "Grace under pressure", we delete that entire record using `var request = cursor.delete();`.

The cursor does not require us to select the data based on a key; we can just grab all of it. Also note that in each iteration of the loop, you can grab data from the current record under the cursor object using `cursor.value.foo`. For a complete working example, see our [IDBCursor example](https://github.com/mdn/IDBcursor-example/) ([view example live](https://mdn.github.io/IDBcursor-example/).)

    function deleteResult() {
      list.textContent = '';
      const transaction = db.transaction(['rushAlbumList'], 'readwrite');
      const objectStore = transaction.objectStore('rushAlbumList');

      objectStore.openCursor().onsuccess = function(event) {
        const cursor = event.target.result;
        if(cursor) {
          if(cursor.value.albumTitle === 'Grace under pressure') {
            const request = cursor.delete();
            request.onsuccess = function() {
              console.log('Deleted that mediocre album from 1984. Even Power windows is better.');
            };
          } else {
            const listItem = document.createElement('li');
            listItem.innerHTML = '<strong>' + cursor.value.albumTitle + '</strong>, ' + cursor.value.year;
            list.appendChild(listItem);
          }
          cursor.continue();
        } else {
          console.log('Entries displayed.');
        }
      };
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbcursor-delete">Indexed Database API 2.0<br />
<span class="small">The definition of 'delete()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbcursor-delete">Indexed Database API 2.0<br />
<span class="small">The definition of 'delete()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`delete`

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

## See also

- [Using IndexedDB](../indexeddb_api/using_indexeddb)
- Starting transactions: [`IDBDatabase`](../idbdatabase)
- Using transactions: [`IDBTransaction`](../idbtransaction)
- Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
- Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
- Using cursors: [`IDBCursor`](../idbcursor)
- Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBCursor/delete" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBCursor/delete</a>
