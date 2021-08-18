# IDBIndex.multiEntry

The `multiEntry` read-only property of the [`IDBIndex`](../idbindex) interface returns a boolean value that affects how the index behaves when the result of evaluating the index's key path yields an array.

This is decided when the index is created, using the [`IDBObjectStore.createIndex`](../idbobjectstore/createindex) method. This method takes an optional `options` parameter whose `multiEntry` property is set to `true`/`false`.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    var isMultiEntry = myIndex.multiEntry;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean):

<table><thead><tr class="header"><th>Value</th><th>Effect</th></tr></thead><tbody><tr class="odd"><td>true</td><td>There is one record in the index for each item in an array of keys.</td></tr><tr class="even"><td>false</td><td>There is one record for each key that is an array.</td></tr></tbody></table>

## Example

In the following example we open a transaction and an object store, then get the index `lName` from a simple contacts database. We then open a basic cursor on the index using [`IDBIndex.openCursor`](opencursor) — this works the same as opening a cursor directly on an `ObjectStore` using [`IDBObjectStore.openCursor`](../idbobjectstore/opencursor) except that the returned records are sorted based on the index, not the primary key.

The multi-entry status of the index is logged to the console: it should be returned as `false`.

Finally, we iterate through each record, and insert the data into an HTML table. For a complete working example, see our [IndexedDB-examples demo repo](https://github.com/mdn/indexeddb-examples/tree/master/idbindex) ([View the example live](https://mdn.github.io/indexeddb-examples/idbindex).)

    function displayDataByIndex() {
      tableEntry.innerHTML = '';
      var transaction = db.transaction(['contactsList'], 'readonly');
      var objectStore = transaction.objectStore('contactsList');

      var myIndex = objectStore.index('lName');
      console.log(myIndex.multiEntry);

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbindex-multientry">Indexed Database API 2.0<br />
<span class="small">The definition of 'multiEntry' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbindex-multientry">Indexed Database API 2.0<br />
<span class="small">The definition of 'multiEntry' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`multiEntry`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBIndex/multiEntry" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBIndex/multiEntry</a>
