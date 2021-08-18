# IDBCursor.update()

The `update()` method of the [`IDBCursor`](../idbcursor) interface returns an [`IDBRequest`](../idbrequest) object, and, in a separate thread, updates the value at the current position of the cursor in the object store. If the cursor points to a record that has just been deleted, a new record is created.

Be aware that you can't call `update()` (or [`IDBCursor.delete()`](delete)) on cursors obtained from [`IDBIndex.openKeyCursor()`](../idbindex/openkeycursor). For such needs, you have to use [`IDBIndex.openCursor()`](../idbindex/opencursor) instead.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    var anIDBRequest = myIDBCursor.update(value);

### Parameters

value  
The new value to be stored at the current position.

### Return value

An [`IDBRequest`](../idbrequest) object on which subsequent events related to this operation are fired.

### Exceptions

This method may raise a [`DOMException`](../domexception) of one of the following types:

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>TransactionInactiveError</code></td><td>This IDBCursor's transaction is inactive.</td></tr><tr class="even"><td><code>ReadOnlyError</code></td><td>The transaction mode is read only.</td></tr><tr class="odd"><td><code>InvalidStateError</code></td><td>The cursor was created using <a href="../idbindex/openkeycursor"><code>IDBIndex.openKeyCursor</code></a>, is currently being iterated, or has iterated past its end.</td></tr><tr class="even"><td><code>DataError</code></td><td><p>The underlying object store uses in-line keys and the property in the value at the object store's key path does not match the key in this cursor's position.</p></td></tr><tr class="odd"><td><code>DataCloneError</code></td><td>The data being stored could not be cloned by the internal structured cloning algorithm.</td></tr></tbody></table>

## Example

In this simple fragment we create a transaction, retrieve an object store, then use a cursor to iterate through all the records in the object store. If the `albumTitle` of the current cursor is "A farewell to kings", we update year the album was released using `const request = cursor.update();`.

Note that you cannot change primary keys using `cursor.update()`, hence us not changing the album title; this would ruin the integrity of the data. In such a situation, you would have to delete the record altogether and then add a new one using [`IDBObjectStore.add`](../idbobjectstore/add). Note also that you can't directly put `cursor.value` into an update call, hence the below example using an intermediary `updateData` variable.

T<span style="line-height: 1.5;">he cursor does not require us to select the data based on a key; we can just grab all of it. Also note that in each iteration of the loop, you can grab data from the current record under the cursor object using </span>`cursor.value.foo`<span style="line-height: 1.5;">. For a complete working example, see our [IDBCursor example](https://github.com/mdn/indexeddb-examples/tree/master/idbcursor)</span><span style="line-height: 1.5;"> (</span>[view example live](https://mdn.github.io/indexeddb-examples/idbcursor/)<span style="line-height: 1.5;">.)</span>

    function updateResult() {
      list.textContent = '';
      const transaction = db.transaction(['rushAlbumList'], 'readwrite');
      const objectStore = transaction.objectStore('rushAlbumList');

      objectStore.openCursor().onsuccess = function(event) {
        const cursor = event.target.result;
        if (cursor) {
          if (cursor.value.albumTitle === 'A farewell to kings') {
            const updateData = cursor.value;

            updateData.year = 2050;
            const request = cursor.update(updateData);
            request.onsuccess = function() {
              console.log('A better album year?');
            };
          };

          const listItem = document.createElement('li');
          listItem.innerHTML = '<strong>' + cursor.value.albumTitle + '</strong>, ' + cursor.value.year;
          list.appendChild(listItem);
          cursor.continue();
        } else {
          console.log('Entries displayed.');
        }
      };
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbcursor-update">Indexed Database API 2.0<br />
<span class="small">The definition of 'update()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbcursor-update">Indexed Database API 2.0<br />
<span class="small">The definition of 'update()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`update`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBCursor/update" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBCursor/update</a>
