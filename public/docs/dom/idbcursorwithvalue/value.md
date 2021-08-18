# IDBCursorWithValue.value

The `value` read-only property of the [`IDBCursorWithValue`](../idbcursorwithvalue) interface returns the value of the current cursor, whatever that is.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    var value = myIDBCursorWithValue.value;

### Value

The value of the current cursor.

## Example

In this example we create a transaction, retrieve an object store, then use a cursor to iterate through all the records in the object store. Within each iteration we log the value of the cursor with `cursor.value`.

T<span style="line-height: 1.5;">he cursor does not require us to select the data based on a key; we can just grab all of it. Also note that in each iteration of the loop, you can grab data from the current record under the cursor object using </span>`cursor.value.foo`<span style="line-height: 1.5;">. For a complete working example, see our [IDBCursor example](https://github.com/mdn/IDBcursor-example/)</span><span style="line-height: 1.5;"> (</span>[view example live](https://mdn.github.io/IDBcursor-example/)<span style="line-height: 1.5;">.)</span>

    function displayData() {
      var transaction = db.transaction(['rushAlbumList'], "readonly");
      var objectStore = transaction.objectStore('rushAlbumList');

      objectStore.openCursor().onsuccess = function(event) {
        var cursor = event.target.result;
        if(cursor) {
          var listItem = document.createElement('li');
          listItem.innerHTML = cursor.value.albumTitle + ', ' + cursor.value.year;
          list.appendChild(listItem);

          console.log(cursor.value);
          cursor.continue();
        } else {
          console.log('Entries all displayed.');
        }
      };
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbcursorwithvalue-value">Indexed Database API 2.0<br />
<span class="small">The definition of 'source' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbcursorwithvalue-value">Indexed Database API 2.0<br />
<span class="small">The definition of 'IDBDatabase' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`value`

23

12

10

10

15

7

Yes

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBCursorWithValue/value" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBCursorWithValue/value</a>
