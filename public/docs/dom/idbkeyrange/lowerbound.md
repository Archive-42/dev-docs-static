IDBKeyRange.lowerBound()
========================

The `lowerBound()` method of the [`IDBKeyRange`](../idbkeyrange) interface creates a new key range with only a lower bound. By default, it includes the lower endpoint value and is closed.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var myIDBKeyRange = IDBKeyRange.lowerBound(lower);
    var myIDBKeyRange = IDBKeyRange.lowerBound(lower, open);

### Parameters

lower   
specifies the lower bound of the new key range.

open <span class="badge inline optional">Optional</span>   
indicates whether the lower bound excludes the endpoint value. The default is false.

### Return value

[`IDBKeyRange`](../idbkeyrange): The newly created key range.

### Exceptions

This method may raise a [`DOMException`](../domexception) of the following type:

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>DataError</code></td><td><p>The value parameter passed was not a valid key.</p></td></tr></tbody></table>

Example
-------

The following example illustrates how you'd use a lower bound key range. Here we declare `keyRangeValue = IDBKeyRange.lowerBound("F", false);` — a range that includes the value "F" and everthing after it. We open a transaction (using [`IDBTransaction`](../idbtransaction)) and an object store, and open a Cursor with [`IDBObjectStore.openCursor`](../idbobjectstore/opencursor), declaring `keyRangeValue` as its optional key range value. This means that the cursor will only retrieve the record with the key value "F" and all that come after it. If we used `IDBKeyRange.lowerBound("F", true);`, then the range would not include "F"; only the values after it.

**Note**: For a more complete example allowing you to experiment with key range, have a look at our [IDBKeyRange-example](https://github.com/mdn/indexeddb-examples/tree/master/idbkeyrange) repo ([view the example live too](https://mdn.github.io/indexeddb-examples/idbkeyrange/).)

    function displayData() {
      var keyRangeValue = IDBKeyRange.lowerBound("F");

      var transaction = db.transaction(['fThings'], 'readonly');
      var objectStore = transaction.objectStore('fThings');

      objectStore.openCursor(keyRangeValue).onsuccess = function(event) {
        var cursor = event.target.result;
          if(cursor) {
            var listItem = document.createElement('li');
            listItem.innerHTML = '<strong>' + cursor.value.fThing + '</strong>, ' + cursor.value.fRating;
            list.appendChild(listItem);

            cursor.continue();
          } else {
            console.log('Entries all displayed.');
          }
        };
      };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbkeyrange-lowerbound">Indexed Database API 2.0<br />
<span class="small">The definition of 'lowerBound()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://w3c.github.io/IndexedDB/#dom-idbkeyrange-lowerbound">Indexed Database API 3.0<br />
<span class="small">The definition of 'lowerBound()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr></tbody></table>

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

`lowerBound`

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

See also
--------

-   [Using IndexedDB](../indexeddb_api/using_indexeddb)
-   Starting transactions: [`IDBDatabase`](../idbdatabase)
-   Using transactions: [`IDBTransaction`](../idbtransaction)
-   Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
-   Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
-   Using cursors: [`IDBCursor`](../idbcursor)
-   Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBKeyRange/lowerBound" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBKeyRange/lowerBound</a>
