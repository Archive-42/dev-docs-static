# IDBIndex.getKey()

The `getKey()` method of the [`IDBIndex`](../idbindex) interface returns an [`IDBRequest`](../idbrequest) object, and, in a separate thread, finds either the primary key that corresponds to the given key in this index or the first corresponding primary key, if `key` is set to an [`IDBKeyRange`](../idbkeyrange).

If a primary key is found, it is set as the `result` of the request object. Note that this doesn't return the whole record as [`IDBIndex.get`](get) does.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    var request = myIndex.getKey(key);

### Parameters

key <span class="badge inline optional">Optional</span>  
A key or [`IDBKeyRange`](../idbkeyrange) that identifies a record to be retrieved. If this value is null or missing, the browser will use an unbound key range.

### Return value

An [`IDBRequest`](../idbrequest) object on which subsequent events related to this operation are fired.

### <span style="line-height: 1.5;">Exceptions</span>

This method may raise a [`DOMException`](../domexception) of one of the following types:

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>TransactionInactiveError</code></td><td>This IDBIndex's transaction is inactive.</td></tr><tr class="even"><td><code>DataError</code></td><td><p>The key or key range provided contains an invalid key.</p></td></tr><tr class="odd"><td><code>InvalidStateError</code></td><td>The IDBIndex has been deleted or removed.</td></tr></tbody></table>

## Example

In the following example we open a transaction and an object store, then get the index `lName` from a simple contacts database. We then open a basic cursor on the index using [`IDBIndex.openCursor`](opencursor) — this works the same as opening a cursor directly on an `ObjectStore` using [`IDBObjectStore.openCursor`](../idbobjectstore/opencursor) except that the returned records are sorted based on the index, not the primary key.

`myIndex.getKey('Bungle')` is then used to retrieve the primary key of the record with an `lName` of `Bungle`, and the result of that request is logged to the console when its success callback returns.

Finally, we iterate through each record, and insert the data into an HTML table. For a complete working example, see our [IndexedDB-examples demo repo](https://github.com/mdn/indexeddb-examples/tree/master/idbindex) ([View the example live](https://mdn.github.io/indexeddb-examples/idbindex).)

    function displayDataByIndex() {
      tableEntry.innerHTML = '';
      var transaction = db.transaction(['contactsList'], 'readonly');
      var objectStore = transaction.objectStore('contactsList');

      var myIndex = objectStore.index('lName');
      var getKeyRequest = myIndex.getKey('Bungle');
      getKeyRequest.onsuccess = function() {
        console.log(getKeyRequest.result);
      }

      myIndex.openCursor().onsuccess = function(event) {
        var cursor = event.target.result;
        if(cursor) {
          var tableRow = document.createElement('tr');
          tableRow.innerHTML =   '<td>' + cursor.value.id + '</td>'
                               + '<td>' + cursor.value.lName + '</td>'
                               + '<td>' + cursor.value.fName + '</td>'
                               + '<td>' + cursor.value.jTitle + '</td>'
                               + '<td>' + cursor.value.company + '</td>'
                               + '<td>' + cursor.value.eMail + '</td>'
                               + '<td>' + cursor.value.phone + '</td>'
                               + '<td>' + cursor.value.age + '</td>';
          tableEntry.appendChild(tableRow);

          cursor.continue();
        } else {
          console.log('Entries all displayed.');
        }
      };
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbindex-getkey">Indexed Database API 2.0<br />
<span class="small">The definition of 'getKey()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbindex-getkey">Indexed Database API 2.0<br />
<span class="small">The definition of 'getKey()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBIndex/getKey" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBIndex/getKey</a>
