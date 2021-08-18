IDBCursor.key
=============

The `key` read-only property of the [`IDBCursor`](../idbcursor) interface returns the key for the record at the cursor's position. If the cursor is outside its range, this is set to undefined. The cursor's key can be any data type.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var key = cursor.key;

### Value

A value of any type.

Example
-------

In this simple fragment we create a transaction, retrieve an object store, then use a cursor to iterate through all the records in the object store. Within each iteration we log the key of the cursor to the console, something like this (its the album title in each case, which is our key).

T<span style="line-height: 1.5;">he cursor does not require us to select the data based on a key; we can just grab all of it. Also note that in each iteration of the loop, you can grab data from the current record under the cursor object using </span>`cursor.value.foo`<span style="line-height: 1.5;">. For a complete working example, see our [IDBCursor example](https://github.com/mdn/indexeddb-examples/tree/master/idbcursor)</span><span style="line-height: 1.5;"> (</span>[view example live](https://mdn.github.io/indexeddb-examples/idbcursor/)<span style="line-height: 1.5;">.)</span>

    function displayData() {
      var transaction = db.transaction(['rushAlbumList'], "readonly");
      var objectStore = transaction.objectStore('rushAlbumList');

      objectStore.openCursor().onsuccess = function(event) {
        var cursor = event.target.result;
        if(cursor) {
          var listItem = document.createElement('li');
          listItem.innerHTML = cursor.value.albumTitle + ', ' + cursor.value.year;
          list.appendChild(listItem);

          console.log(cursor.key);
          cursor.continue();
        } else {
          console.log('Entries all displayed.');
        }
      };
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbcursor-key">Indexed Database API 2.0<br />
<span class="small">The definition of 'key' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbcursor-key">Indexed Database API 2.0<br />
<span class="small">The definition of 'key' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`key`

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

`binary_keys`

58

≤79

51

?

45

10.1

58

58

?

43

10.3

7.0

See also
--------

-   [Using IndexedDB](../indexeddb_api/using_indexeddb)
-   Starting transactions: [`IDBDatabase`](../idbdatabase)
-   Using transactions: [`IDBTransaction`](../idbtransaction)
-   Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
-   Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
-   Using cursors: [`IDBCursor`](../idbcursor)
-   Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBCursor/key" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBCursor/key</a>
