IDBCursor.advance()
===================

The `advance()` method of the [`IDBCursor`](../idbcursor) interface sets the num<span style="line-height: 1.5;">ber of times a cursor should move its position forward.</span>

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    cursor.advance(count);

### Parameters

`count`  
The number of times to move the cursor forward.

### Exceptions

<span style="line-height: 1.5;">This method may raise a [`DOMException`](../domexception) of one of the following types:</span>

<table><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>TransactionInactiveError</code></td><td>This IDBCursor's transaction is inactive.</td></tr><tr class="even"><td><code>TypeError</code></td><td>The value passed into the <code>count</code> parameter was zero or a negative number.</td></tr><tr class="odd"><td><code>InvalidStateError</code></td><td>The cursor is currently being iterated or has iterated past its end.<br />
</td></tr></tbody></table>

Example
-------

In this simple fragment we create a transaction, retrieve an object store, then use a cursor to iterate through the records in the object store. Here we use `cursor.advance(2)` to jump 2 places forward each time, meaning that only every other result will be displayed. `advance()` works in a similar way to [`IDBCursor.continue`](continue), except that it allows you to jump multiple records at a time, not just always go onto the next record.

<span style="line-height: 1.5;">Note that in each iteration of the loop, you can grab data from the current record under the cursor object using </span>`cursor.value.foo`<span style="line-height: 1.5;">. For a complete working example, see our [IDBCursor example](https://github.com/mdn/indexeddb-examples/tree/master/idbcursor)</span><span style="line-height: 1.5;"> (</span>[view example live](https://mdn.github.io/indexeddb-examples/idbcursor/)<span style="line-height: 1.5;">.)</span>

    function advanceResult() {
      list.textContent = '';
      const transaction = db.transaction(['rushAlbumList'], "readonly");
      const objectStore = transaction.objectStore('rushAlbumList');

      objectStore.openCursor().onsuccess = function(event) {
        const cursor = event.target.result;
        if(cursor) {
          const listItem = document.createElement('li');
          listItem.innerHTML = '<strong>' + cursor.value.albumTitle + '</strong>, ' + cursor.value.year;
          list.appendChild(listItem);
          cursor.advance(2);
        } else {
          console.log('Every other entry displayed.');
        }
      };
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbcursor-advance">Indexed Database API 2.0<br />
<span class="small">The definition of 'advance()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbcursor-advance">Indexed Database API 2.0<br />
<span class="small">The definition of 'advance()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`advance`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBCursor/advance" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBCursor/advance</a>
