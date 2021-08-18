IDBCursor.direction
===================

The `direction` read-only property of the [`IDBCursor`](../idbcursor) interface is a [`DOMString`](../domstring) that returns the direction of traversal of the cursor (set using [`IDBObjectStore.openCursor`](../idbobjectstore/opencursor) for example). See the [Values](#values) section below for possible values.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var direction = cursor.direction;

### Value

A string (defined by the [`IDBCursorDirection` enum](https://w3c.github.io/IndexedDB/#enumdef-idbcursordirection)) indicating the direction in which the cursor is traversing the data. Possible values are:

<table><thead><tr class="header"><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>next</code></td><td>This direction causes the cursor to be opened at the start of the <span class="internalDFN">source</span>.</td></tr><tr class="even"><td><code>nextunique</code></td><td>This direction causes the cursor to be opened at the start of the <span class="internalDFN">source</span>. For every key with duplicate values, only the first record is yielded.</td></tr><tr class="odd"><td><code>prev</code></td><td>This direction causes the cursor to be opened at the end of the <span class="internalDFN">source</span>.</td></tr><tr class="even"><td><code>prevunique</code></td><td>This direction causes the cursor to be opened at the end of the <span class="internalDFN">source</span>. For every key with duplicate values, only the first record is yielded.<br />
</td></tr></tbody></table>

Example
-------

In this simple fragment we create a transaction, retrieve an object store, then use a cursor to iterate through all the records in the object store. Within each iteration we log the direction of the cursor, something like this:

    prev

**Note**: we can't change the direction of travel of the cursor using the `direction` property, as it is read-only. We specify the direction of travel using the 2nd argument of [`IDBObjectStore.openCursor`](../idbobjectstore/opencursor).

The cursor does not require us to select the data based on a key; we can just grab all of it. Also note that in each iteration of the loop, you can grab data from the current record under the cursor object using `cursor.value.foo`. For a complete working example, see our [IDBCursor example](https://github.com/mdn/indexeddb-examples/tree/master/idbcursor) ([view example live](https://mdn.github.io/indexeddb-examples/idbcursor/).)

    function backwards() {
      list.textContent = '';
      const transaction = db.transaction(['rushAlbumList'], 'readonly');
      const objectStore = transaction.objectStore('rushAlbumList');

      objectStore.openCursor(null,'prev').onsuccess = function(event) {
        const cursor = event.target.result;
          if(cursor) {
            const listItem = document.createElement('li');
            listItem.innerHTML = '<strong>' + cursor.value.albumTitle + '</strong>, ' + cursor.value.year;
            list.appendChild(listItem);

            console.log(cursor.direction);
            cursor.continue();
          } else {
            console.log('Entries displayed backwards.');
          }
      };
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbcursor-direction">Indexed Database API 2.0<br />
<span class="small">The definition of 'direction' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbcursor-direction">Indexed Database API 2.0<br />
<span class="small">The definition of 'direction' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`direction`

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

See also
--------

-   [Using IndexedDB](../indexeddb_api/using_indexeddb)
-   Starting transactions: [`IDBDatabase`](../idbdatabase)
-   Using transactions: [`IDBTransaction`](../idbtransaction)
-   Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
-   Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
-   Using cursors: [`IDBCursor`](../idbcursor)
-   Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBCursor/direction" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBCursor/direction</a>
