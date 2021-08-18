IDBCursor.continue()
====================

The `continue()` method of the [`IDBCursor`](../idbcursor) interface advances the cursor to the next position along its direction, to the item whose key matches the optional key parameter. If no key is specified, the cursor advances to the immediate next position, based on its direction.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    cursor.continue(key);

### Parameters

 `key` <span class="badge inline optional">Optional</span>   
The key to position the cursor at.

### Exceptions

This method may raise a [`DOMException`](../domexception) of one of the following types:

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>TransactionInactiveError</code></td><td>This IDBCursor's transaction is inactive.</td></tr><tr class="even"><td><code>DataError</code></td><td><p>The key parameter may have any of the following conditions:</p><ul><li>The key is not a valid key.</li><li>The key is less than or equal to this cursor's position and the cursor's direction is <code>next</code> or <code>nextunique</code>.</li><li>The key is greater than or equal to this cursor's position and this cursor's direction is <code>prev</code> or <code>prevunique</code>.</li></ul></td></tr><tr class="odd"><td><code>InvalidStateError</code></td><td>The cursor is currently being iterated or has iterated past its end.</td></tr></tbody></table>

Example
-------

In this simple fragment we create a transaction, retrieve an object store, then use a cursor to iterate through all the records in the object store. The cursor does not require us to select the data based on a key; we can just grab all of it. Also note that in each iteration of the loop, you can grab data from the current record under the cursor object using `cursor.value.foo`. For a complete working example, see our [IDBCursor example](https://github.com/mdn/indexeddb-examples/tree/master/idbcursor) ([view example live](https://mdn.github.io/indexeddb-examples/idbcursor/).)

    function displayData() {
      var transaction = db.transaction(['rushAlbumList'], "readonly");
      var objectStore = transaction.objectStore('rushAlbumList');

      objectStore.openCursor().onsuccess = function(event) {
        var cursor = event.target.result;
        if(cursor) {
          var listItem = document.createElement('li');
          listItem.innerHTML = cursor.value.albumTitle + ', ' + cursor.value.year;
          list.appendChild(listItem);

          cursor.continue();
        } else {
          console.log('Entries all displayed.');
        }
      };
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbcursor-continue">Indexed Database API 2.0<br />
<span class="small">The definition of 'continue()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbcursor-continue">Indexed Database API 2.0<br />
<span class="small">The definition of 'continue()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`continue`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBCursor/continue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBCursor/continue</a>
