# IDBKeyRange.upperOpen

The `upperOpen` read-only property of the [`IDBKeyRange`](../idbkeyrange) interface returns a boolean indicating whether the upper-bound value is included in the key range.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    var upperOpen = myKeyRange.upperOpen

### Value

<span style="line-height: 1.5;">A [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean):</span>

<table><thead><tr class="header"><th>Value</th><th>Indication</th></tr></thead><tbody><tr class="odd"><td><code>true</code></td><td>The upper-bound value is not included in the key range.</td></tr><tr class="even"><td><code>false</code></td><td>The upper-bound value is included in the key range.<br />
</td></tr></tbody></table>

## Example

The following example illustrates how you'd use a key range. Here we declare `keyRangeValue = IDBKeyRange.upperBound("F", "W", true, true);` — a range that includes everything between "F" and "W" but not including them — since both the upper and lower bounds have been declared as open (`true`). We open a transaction (using [`IDBTransaction`](../idbtransaction)) and an object store, and open a Cursor with [`IDBObjectStore.openCursor`](../idbobjectstore/opencursor), declaring `keyRangeValue` as its optional key range value.

After declaring the key range, we log its `upperOpen` property value to the console, which should appear as "true": the upper bound is open, so won't be included in the range.

**Note**: For a more complete example allowing you to experiment with key range, have a look at our [IDBKeyRange-example](https://github.com/mdn/IDBKeyRange-example) repo ([view the example live too](https://mdn.github.io/IDBKeyRange-example/).)

    function displayData() {
      var keyRangeValue = IDBKeyRange.bound("F", "W", true, true);
      console.log(keyRangeValue.upperOpen);

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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbkeyrange-upperopen">Indexed Database API 2.0<br />
<span class="small">The definition of 'upperOpen' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbkeyrange-upperopen">Indexed Database API 2.0<br />
<span class="small">The definition of 'upperOpen' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`upperOpen`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBKeyRange/upperOpen" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBKeyRange/upperOpen</a>
