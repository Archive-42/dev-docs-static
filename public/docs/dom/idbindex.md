# IDBIndex

`IDBIndex` interface of the [IndexedDB API](indexeddb_api) provides asynchronous access to an [index](indexeddb_api/basic_concepts_behind_indexeddb#gloss_index) in a database. An index is a kind of object store for looking up records in another object store, called the referenced object store. You use this interface to retrieve data.

You can retrieve records in an object store through the primary key or by using an index. An index lets you look up records in an object store using properties of the values in the object stores records other than the primary key

The index is a persistent key-value storage where the value part of its records is the key part of a record in the referenced object store. The records in an index are automatically populated whenever records in the referenced object store are inserted, updated, or deleted. Each record in an index can point to only one record in its referenced object store, but several indexes can reference the same object store. When the object store changes, all indexes that refers to the object store are automatically updated.

<span style="line-height: 1.5;">You can grab a set of keys within a range. To learn more, see [`IDBKeyRange`](idbkeyrange).</span>

**Note:** This feature is available in [Web Workers](web_workers_api).

## Properties

[`IDBIndex.isAutoLocale`](idbindex/isautolocale) <span class="badge inline readonly">Read only </span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the index had a `locale` value of `auto` specified upon its creation (see [`createIndex()`'s optionalParameters](idbobjectstore/createindex#parameters).)

[`IDBIndex.locale`](idbindex/locale) <span class="badge inline readonly">Read only </span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Returns the locale of the index (for example `en-US`, or `pl`) if it had a `locale` value specified upon its creation (see [`createIndex()`'s optionalParameters](idbobjectstore/createindex#parameters).)

[`IDBIndex.name`](idbindex/name)  
The name of this index.

[`IDBIndex.objectStore`](idbindex/objectstore) <span class="badge inline readonly">Read only </span>  
The name of the object store referenced by this index.

[`IDBIndex.keyPath`](idbindex/keypath) <span class="badge inline readonly">Read only </span>  
The [key path](indexeddb_api#gloss_key_path) of this index. If null, this index is not [auto-populated](#gloss_auto-populated).

[`IDBIndex.multiEntry`](idbindex/multientry) <span class="badge inline readonly">Read only </span>  
Affects how the index behaves when the result of evaluating the index's key path yields an array. If `true`, there is one record in the index for each item in an array of keys. If `false`, then there is one record for each key that is an array.

[`IDBIndex.unique`](idbindex/unique) <span class="badge inline readonly">Read only </span>  
If `true`, this index does not allow duplicate values for a key.

## Methods

Inherits from: [EventTarget](eventtarget)

[`IDBIndex.count()`](idbindex/count)  
Returns an [`IDBRequest`](idbrequest) object, and in a separate thread, returns the number of records within a key range.

[`IDBIndex.get()`](idbindex/get)  
Returns an [`IDBRequest`](idbrequest) object, and, in a separate thread, finds either the value in the referenced object store that corresponds to the given key or the first corresponding value, if `key` is an [`IDBKeyRange`](idbkeyrange).

[`IDBIndex.getKey()`](idbindex/getkey)  
Returns an [`IDBRequest`](idbrequest) object, and, in a separate thread, finds either the given key or the primary key, if `key` is an [`IDBKeyRange`](idbkeyrange).

[`IDBIndex.getAll()`](idbindex/getall)  
Returns an [`IDBRequest`](idbrequest) object, in a separate thread, finds all matching values in the referenced object store that correspond to the given key or are in range, if `key` is an [`IDBKeyRange`](idbkeyrange).

[`IDBIndex.getAllKeys()`](idbindex/getallkeys)  
Returns an [`IDBRequest`](idbrequest) object, in a separate thread, finds all matching keys in the referenced object store that correspond to the given key or are in range, if `key` is an [`IDBKeyRange`](idbkeyrange).

[`IDBIndex.openCursor()`](idbindex/opencursor)  
Returns an [`IDBRequest`](idbrequest) object, and, in a separate thread, creates a [cursor](indexeddb_api#gloss_cursor) over the specified key range.

[`IDBIndex.openKeyCursor()`](idbindex/openkeycursor)  
Returns an [`IDBRequest`](idbrequest) object, and, in a separate thread, creates a cursor over the specified key range, as arranged by this index.

## Example

In the following example we open a transaction and an object store, then get the index `lName` from a simple contacts database. We then open a basic cursor on the index using [`IDBIndex.openCursor`](idbindex/opencursor) — this works the same as opening a cursor directly on an `ObjectStore` using [`IDBObjectStore.openCursor`](idbobjectstore/opencursor) except that the returned records are sorted based on the index, not the primary key.

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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#idbindex">Indexed Database API 2.0<br />
<span class="small">The definition of 'IDBIndex' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#index-interface">Indexed Database API 2.0<br />
<span class="small">The definition of 'IDBIndex' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`IDBIndex`

24

23-57

12

16

10-16

10

15

7

≤37

≤37-57

25

25-57

22

14

8

1.5

1.5-7.0

`count`

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

`get`

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

`getAll`

48

≤18

44

No

35

10.1

48

48

44

35

10.3

5.0

`getAllKeys`

48

≤18

44

No

35

10.1

48

48

44

35

10.3

5.0

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

`isAutoLocale`

No

No

43

No

No

No

No

No

43

No

No

No

`keyPath`

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

`locale`

No

No

43

No

No

No

No

No

43

No

No

No

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

`objectStore`

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

`openKeyCursor`

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

`unique`

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

`worker_support`

Yes

≤18

37

?

Yes

?

Yes

Yes

37

Yes

?

Yes

## See also

- [Using IndexedDB](indexeddb_api/using_indexeddb)
- Starting transactions: [`IDBDatabase`](idbdatabase)
- Using transactions: [`IDBTransaction`](idbtransaction)
- Setting a range of keys: [`IDBKeyRange`](idbkeyrange)
- Retrieving and making changes to your data: [`IDBObjectStore`](idbobjectstore)
- Using cursors: [`IDBCursor`](idbcursor)
- Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBIndex" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBIndex</a>
