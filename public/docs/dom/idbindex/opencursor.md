IDBIndex.openCursor()
=====================

The `openCursor()` method of the [`IDBIndex`](../idbindex) interface returns an [`IDBRequest`](../idbrequest) object, and, in a separate thread, creates a [cursor](../indexeddb_api#gloss_cursor) over the specified key range.

The method sets the position of the cursor to the appropriate record, based on the specified direction.

If the key range is not specified or is null, then the range includes all the records.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var request = myIndex.openCursor();
    var request = myIndex.openCursor(range);
    var request = myIndex.openCursor(range, direction);

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

Example
-------

In the following example we open a transaction and an object store, then get the index `lName` from a simple contacts database. We then open a basic cursor on the index using `openCursor()` — this works the same as opening a cursor directly on an `ObjectStore` using [`IDBObjectStore.openCursor`](../idbobjectstore/opencursor) except that the returned records are sorted based on the index, not the primary key.

Finally, we iterate through each record, and insert the data into an HTML table. For a complete working example, see our [IndexedDB-examples demo repo](https://github.com/mdn/indexeddb-examples/tree/master/idbindex) ([View the example live](https://mdn.github.io/indexeddb-examples/idbindex).)

    function displayDataByIndex() {
      tableEntry.innerHTML = '';
      var transaction = db.transaction(['contactsList'], 'readonly');
      var objectStore = transaction.objectStore('contactsList');

      var myIndex = objectStore.index('lName');

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

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbindex-opencursor">Indexed Database API 2.0<br />
<span class="small">The definition of 'openCursor()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbindex-opencursor">Indexed Database API 2.0<br />
<span class="small">The definition of 'openCursor()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

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

`openCursor`

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

See also
--------

-   [Using IndexedDB](../indexeddb_api/using_indexeddb)
-   Starting transactions: [`IDBDatabase`](../idbdatabase)
-   Using transactions: [`IDBTransaction`](../idbtransaction)
-   Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
-   Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
-   Using cursors: [`IDBCursor`](../idbcursor)
-   Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBIndex/openCursor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBIndex/openCursor</a>
