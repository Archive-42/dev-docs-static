# IDBIndex.name

The `name` property of the [`IDBIndex`](../idbindex) interface contains a string which names the index.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    var indexName = IDBIndex.name;
    IDBIndex.name = indexName;

### Value

A [`DOMString`](../domstring) specifying a name for the index.

### Exceptions

There are a several exceptions which can occur when you attempt to change an index's name.

`InvalidStateError`  
The index, or its object store, has been deleted; or the current transaction is not an upgrade transaction. You can only rename indexes during upgrade transactions; that is, when the mode is `"versionchange"`.

`TransactionInactiveError`  
The current transaction is not active.

`ConstraintError`  
An index is already using the specified `name`.

## Example

In the following example we open a transaction and an object store, then get the index `lName` from a simple contacts database. We then open a basic cursor on the index using [`IDBIndex.openCursor()`](opencursor) — this works the same as opening a cursor directly on an [`IDBObjectStore`](../idbobjectstore) using [`openCursor()`](../idbobjectstore/opencursor) except that the returned records are sorted based on the index, not the primary key.

The name of the index is logged to the console: it should be returned as `lName`.

Finally, we iterate through each record, inserting the data into an HTML table. For a complete working example, see our [IndexedDB-examples demo repo](https://github.com/mdn/indexeddb-examples/tree/master/idbindex) ([View the example live](https://mdn.github.io/indexeddb-examples/idbindex)).

    function displayDataByIndex() {
      tableEntry.innerHTML = '';
      var transaction = db.transaction(['contactsList'], 'readonly');
      var objectStore = transaction.objectStore('contactsList');

      var myIndex = objectStore.index('lName');
      console.log(myIndex.name);

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbindex-name">Indexed Database API 2.0<br />
<span class="small">The definition of 'name' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbindex-name">Indexed Database API 2.0<br />
<span class="small">The definition of 'name' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`name`

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

`renaming_with_name_setter`

Yes

≤79

49

?

?

?

Yes

Yes

?

?

?

Yes

## See also

- [Using IndexedDB](../indexeddb_api/using_indexeddb)
- Starting transactions: [`IDBDatabase`](../idbdatabase)
- Using transactions: [`IDBTransaction`](../idbtransaction)
- Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
- Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
- Using cursors: [`IDBCursor`](../idbcursor)
- Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBIndex/name" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBIndex/name</a>
