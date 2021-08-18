# IDBKeyRange.bound()

The `bound()` method of the [`IDBKeyRange`](../idbkeyrange) interface creates a new key range with the specified upper and lower bounds. The bounds can be open (that is, the bounds exclude the endpoint values) or closed (that is, the bounds include the endpoint values). By default, the bounds are closed.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    var myIDBKeyRange = IDBKeyRange.bound(lower, upper);
    var myIDBKeyRange = IDBKeyRange.bound(lower, upper, lowerOpen);
    var myIDBKeyRange = IDBKeyRange.bound(lower, upper, lowerOpen, upperOpen);

### Parameters

lower  
specifies the lower bound of the new key range.

upper  
specifies the upper bound of the new key range.

lowerOpen <span class="badge inline optional">Optional</span>  
indicates whether the lower bound excludes the endpoint value. The default is false.

upperOpen <span class="badge inline optional">Optional</span>  
Indicates whether the upper bound excludes the endpoint value. The default is false.

### Return value

[`IDBKeyRange`](../idbkeyrange): The newly created key range.

### <span style="line-height: 1.5;">Exceptions</span>

<span style="line-height: 1.5;">This method may raise a [`DOMException`](../domexception) of the following type:</span>

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>DataError</code></td><td><p>The following conditions raise an exception:</p><ul><li>The lower or upper parameters were not passed a valid key.</li><li>The lower key is greater than the upper key.</li><li>The lower key and upper key match and either of the bounds are open.</li></ul></td></tr></tbody></table>

## Example

The following example illustrates how you'd use a bound key range. Here we declare a `keyRangeValue = IDBKeyRange.bound("A", "F");` — a range between values of "A" and "F". We open a transaction (using [`IDBTransaction`](../idbtransaction)) and an object store, and open a Cursor with [`IDBObjectStore.openCursor`](../idbobjectstore/opencursor), declaring `keyRangeValue` as its optional key range value. This means that the cursor will only retrieve records with keys inside that range. This range includes the values "A" and "F", as we haven't declared that they should be open bounds. If we used IDBKeyRange.bound("A", "F", true, true);, then the range would not include "A" and "F", only the values between them.

**Note**: For a more complete example allowing you to experiment with key range, have a look at the idbkeyrange directory [in the indexeddb-examples](https://github.com/mdn/indexeddb-examples/tree/master/idbkeyrange) repo ([view the example live too](https://mdn.github.io/indexeddb-examples/idbkeyrange/).)

    function displayData() {
      var keyRangeValue = IDBKeyRange.bound("A", "F");

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbkeyrange-bound">Indexed Database API 2.0<br />
<span class="small">The definition of 'bound()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbkeyrange-bound">Indexed Database API 2.0<br />
<span class="small">The definition of 'bound()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`bound`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBKeyRange/bound" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBKeyRange/bound</a>
