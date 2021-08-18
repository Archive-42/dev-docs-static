# IDBCursor

**Note:** Not to be confused with [`IDBCursorWithValue`](idbcursorwithvalue) which is just an `IDBCursor` interface with an additional `value` property.

The `IDBCursor` interface of the [IndexedDB API](indexeddb_api) represents a [cursor](indexeddb_api/basic_concepts_behind_indexeddb#gloss_cursor) for traversing or iterating over multiple records in a database.

The cursor has a source that indicates which index or object store it is iterating over. It has a position within the range, and moves in a direction that is increasing or decreasing in the order of record keys. The cursor enables an application to asynchronously process all the records in the cursor's range.

You can have an unlimited number of cursors at the same time. You always get the same `IDBCursor` object representing a given cursor. Operations are performed on the underlying index or object store.

**Note:** This feature is available in [Web Workers](web_workers_api).

## Properties

**Note:** [`IDBCursorWithValue`](idbcursorwithvalue) is an `IDBCursor` interface with an additional `value` property.

[`IDBCursor.source`](idbcursor/source) <span class="badge inline readonly">Read only </span>  
Returns the [`IDBObjectStore`](idbobjectstore) or [`IDBIndex`](idbindex) that the cursor is iterating. This function never returns null or throws an exception, even if the cursor is currently being iterated, has iterated past its end, or its transaction is not active.

[`IDBCursor.direction`](idbcursor/direction) <span class="badge inline readonly">Read only </span>  
Returns the direction of traversal of the cursor. See [Constants](#const_next) for possible values.

[`IDBCursor.key`](idbcursor/key) <span class="badge inline readonly">Read only </span>  
Returns the key for the record at the cursor's position. If the cursor is outside its range, this is set to `undefined`. The cursor's key can be any data type.

[`IDBCursor.primaryKey`](idbcursor/primarykey) <span class="badge inline readonly">Read only </span>  
Returns the cursor's current effective primary key. If the cursor is currently being iterated or has iterated outside its range, this is set to `undefined`. The cursor's primary key can be any data type.

[`IDBCursor.request`](idbcursor/request) <span class="badge inline readonly">Read only </span>  
Returns the [`IDBRequest`](idbrequest) that was used to obtain the cursor.

## Methods

[`IDBCursor.advance()`](idbcursor/advance)  
Sets the number of times a cursor should move its position forward.

[`IDBCursor.continue()`](idbcursor/continue)  
Advances the cursor to the next position along its direction, to the item whose key matches the optional `key` parameter.

[`IDBCursor.continuePrimaryKey()`](idbcursor/continueprimarykey)  
Sets the cursor to the given index key and primary key given as arguments.

[`IDBCursor.delete()`](idbcursor/delete)  
Returns an [`IDBRequest`](idbrequest) object, and, in a separate thread, deletes the record at the cursor's position, without changing the cursor's position. This can be used to delete specific records.

[`IDBCursor.update()`](idbcursor/update)  
Returns an [`IDBRequest`](idbrequest) object, and, in a separate thread, updates the value at the current position of the cursor in the object store. This can be used to update specific records.

## Constants

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

These constants are no longer available — they were removed in Gecko 25. You should use the string constants directly instead. ([bug 891944](https://bugzilla.mozilla.org/show_bug.cgi?id=891944))

- `NEXT `: `"next"` : The cursor shows all records, including duplicates. It starts at the lower bound of the key range and moves upwards (monotonically increasing in the order of keys).
- `NEXTUNIQUE` : `"nextunique"` : The cursor shows all records, excluding duplicates. If multiple records exist with the same key, only the first one iterated is retrieved. It starts at the lower bound of the key range and moves upwards.
- `PREV `: `"prev"` : The cursor shows all records, including duplicates. It starts at the upper bound of the key range and moves downwards (monotonically decreasing in the order of keys).
- `PREVUNIQUE `: `"prevunique"` : The cursor shows all records, excluding duplicates. If multiple records exist with the same key, only the first one iterated is retrieved. It starts at the upper bound of the key range and moves downwards.

## Examples

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
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#cursor-interface">Indexed Database API 2.0<br />
<span class="small">The definition of 'cursor' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#cursor-interface">Indexed Database API 2.0<br />
<span class="small">The definition of 'cursor' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Added <code>continuePrimaryKey()</code> and support for binary keys, and the <a href="idbcursor/request"><code>IDBCursor.request</code></a> property.</td></tr></tbody></table>

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

`IDBCursor`

24

23-57

12

16

10-16

10

44

15-44

7

≤37

≤37-57

25

25-57

22

43

14-43

8

1.5

1.5-7.0

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

`continuePrimaryKey`

58

79

10

No

45

10.1

58

58

51

43

10.3

7.0

`delete`

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

`primaryKey`

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

`request`

76

79

77

No

63

No

76

76

No

54

No

12.0

`source`

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

`update`

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

`worker_support`

23

≤18

37

?

15

7

≤37

25

37

14

?

1.5

## See also

- [Using IndexedDB](indexeddb_api/using_indexeddb)
- Starting transactions: [`IDBDatabase`](idbdatabase)
- Using transactions: [`IDBTransaction`](idbtransaction)
- Setting a range of keys: [`IDBKeyRange`](idbkeyrange)
- Retrieving and making changes to your data: [`IDBObjectStore`](idbobjectstore)
- Using cursors: [`IDBCursor`](idbcursor)
- Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBCursor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBCursor</a>
