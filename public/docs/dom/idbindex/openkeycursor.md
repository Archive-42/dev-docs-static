# IDBIndex.openKeyCursor()

The `openKeyCursor()` method of the [`IDBIndex`](../idbindex) interface returns an [`IDBRequest`](../idbrequest) object, and, in a separate thread, creates a cursor over the specified key range, as arranged by this index.

The method sets the position of the cursor to the appropriate key, based on the specified direction.

If the key range is not specified or is null, then the range includes all the keys.

**Note:** Cursors returned by `openKeyCursor()` do not make the referenced value available as [`IDBIndex.openCursor`](opencursor) does. This makes obtaining a list of keys much more efficient.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    var request = myIndex.openKeyCursor();
    var request = myIndex.openKeyCursor(range);
    var request = myIndex.openKeyCursor(range, direction);

### Parameters

range <span class="badge inline optional">Optional</span>  
A key or [`IDBKeyRange`](../idbkeyrange) to use as the cursor's range. If nothing is passed, this will default to a key range that selects all the records in this object store.

direction <span class="badge inline optional">Optional</span>  
The cursor's [direction](../idbcursor#constants). See [IDBCursor Constants](../idbcursor#constants) for possible values.

### Return value

An [`IDBRequest`](../idbrequest) object on which subsequent events related to this operation are fired.

### Exceptions

This method may raise a [`DOMException`](../domexception) of one of the following types:

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>TransactionInactiveError</code></td><td>This <a href="../idbindex"><code>IDBIndex</code></a>'s transaction is inactive.</td></tr><tr class="even"><td><code>TypeError</code></td><td>The value for the direction parameter is invalid.</td></tr><tr class="odd"><td><code>DataError</code></td><td><p>The key or key range provided contains an invalid key.</p></td></tr><tr class="even"><td><code>InvalidStateError</code></td><td>The <a href="../idbindex"><code>IDBIndex</code></a> has been deleted or removed.</td></tr></tbody></table>

## Example

In the following example we open a transaction and an object store, then get the index `lName` from a simple contacts database. We then open a key cursor on the index using `openKeyCursor()` — this works the same as opening a cursor directly on an `ObjectStore` using [`IDBObjectStore.openKeyCursor`](../idbobjectstore/openkeycursor) except that the returned records are sorted based on the index, not the primary key.

Finally, we iterate through each record in the index, and insert the last name and the corresponding primary key of the referenced record into an HTML table.

    function displayDataByIndex() {
      tableEntry.innerHTML = '';
      var transaction = db.transaction(['contactsList'], 'readonly');
      var objectStore = transaction.objectStore('contactsList');

      var myIndex = objectStore.index('lName');

      myIndex.openKeyCursor().onsuccess = function(event) {
        var cursor = event.target.result;
        if(cursor) {
          var tableRow = document.createElement('tr');
          tableRow.innerHTML =   '<td>' + cursor.key + '</td>'
                               + '<td>' + cursor.primaryKey + '</td>';
          tableEntry.appendChild(tableRow);

          cursor.continue();
        } else {
          console.log('All last names displayed.');
        }
      };
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbindex-openkeycursor">Indexed Database API 2.0<br />
<span class="small">The definition of 'openKeyCursor()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbindex-openkeycursor">Indexed Database API 2.0<br />
<span class="small">The definition of 'openKeyCursor()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`openKeyCursor`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBIndex/openKeyCursor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBIndex/openKeyCursor</a>
