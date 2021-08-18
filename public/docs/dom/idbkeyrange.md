IDBKeyRange
===========

The `IDBKeyRange` interface of the [IndexedDB API](indexeddb_api) represents a continuous interval over some data type that is used for keys. Records can be retrieved from [`IDBObjectStore`](idbobjectstore) and [`IDBIndex`](idbindex) objects using keys or a range of keys. You can limit the range using lower and upper bounds. For example, you can iterate over all values of a key in the value range A–Z.

A key range can be a single value or a range with upper and lower bounds or endpoints. If the key range has both upper and lower bounds, then it is *bounded*; if it has no bounds, it is *unbounded*. A bounded key range can either be open (the endpoints are excluded) or closed (the endpoints are included). To retrieve all keys within a certain range, you can use the following code constructs:

Range

Code

All keys ≥ **x**

[`IDBKeyRange.lowerBound`](idbkeyrange/lowerbound)`(x)`

All keys &gt; **x**

[`IDBKeyRange.lowerBound`](idbkeyrange/lowerbound)`(x, true) `

All keys ≤ **y**

[`IDBKeyRange.upperBound`](idbkeyrange/upperbound)`(y)`

All keys &lt; **y**

[`IDBKeyRange.upperBound`](idbkeyrange/upperbound)`(y, true)`

All keys ≥ **x** && ≤ **y**

[`IDBKeyRange.bound`](idbkeyrange/bound)`(x, y)`

All keys &gt; **x** &&&lt; **y**

[`IDBKeyRange.bound`](idbkeyrange/bound)`(x, y, true, true)`

All keys &gt; **x** && ≤ **y**

[`IDBKeyRange.bound`](idbkeyrange/bound)`(x, y, true, false)`

All keys ≥ **x** &&&lt; **y**

[`IDBKeyRange.bound`](idbkeyrange/bound)`(x, y, false, true)`

The key = **z**

[`IDBKeyRange.only`](idbkeyrange/only)`(z)`

A key is in a key range if the following conditions are true:

-   The lower value of the key range is one of the following:
    -   `undefined`
    -   Less than key value
    -   Equal to key value if `lowerOpen` is `false`.
-   The upper value of the key range is one of the following:
    -   `undefined`
    -   Greater than key value
    -   Equal to key value if `upperOpen` is `false`.

**Note:** This feature is available in [Web Workers](web_workers_api).

Properties
----------

 [`IDBKeyRange.lower`](idbkeyrange/lower) <span class="badge inline readonly">Read only </span>   
Lower bound of the key range.

 [`IDBKeyRange.upper`](idbkeyrange/upper) <span class="badge inline readonly">Read only </span>   
Upper bound of the key range.

 [`IDBKeyRange.lowerOpen`](idbkeyrange/loweropen) <span class="badge inline readonly">Read only </span>   
Returns false if the lower-bound value is included in the key range.

 [`IDBKeyRange.upperOpen`](idbkeyrange/upperopen) <span class="badge inline readonly">Read only </span>   
Returns false if the upper-bound value is included in the key range.

Methods
-------

### Static methods

[`IDBKeyRange.bound()`](idbkeyrange/bound)  
Creates a new key range with upper and lower bounds.

[`IDBKeyRange.only()`](idbkeyrange/only)  
Creates a new key range containing a single value.

[`IDBKeyRange.lowerBound()`](idbkeyrange/lowerbound)  
Creates a new key range with only a lower bound.

[`IDBKeyRange.upperBound()`](idbkeyrange/upperbound)  
Creates a new upper-bound key range.

### Instance methods

[`IDBKeyRange.includes()`](idbkeyrange/includes)  
Returns a boolean indicating whether a specified key is inside the key range.

Examples
--------

The following example illustrates how you'd use a key range. Here we declare a `keyRangeValue` as a range between values of "A" and "F". We open a transaction (using [`IDBTransaction`](idbtransaction)) and an object store, and open a Cursor with [`IDBObjectStore.openCursor`](idbobjectstore/opencursor), declaring `keyRangeValue` as its optional key range value. This means that the cursor will only retrieve records with keys inside that range. This range includes the values "A" and "F", as we haven't declared that they should be open bounds. If we used IDBKeyRange.bound("A", "F", true, true);, then the range would not include "A" and "F", only the values between them.

**Note**: For a more complete example allowing you to experiment with key range, have a look at our [IDBKeyRange-example](https://github.com/mdn/indexeddb-examples/tree/master/idbkeyrange) repo ([view the example live too](https://mdn.github.io/indexeddb-examples/idbkeyrange/).)

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
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#idbkeyrange">Indexed Database API 2.0<br />
<span class="small">The definition of 'IDBKeyRange' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#keyrange">Indexed Database API 2.0<br />
<span class="small">The definition of 'IDBKeyRange' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Adds <code>includes()</code>.</td></tr></tbody></table>

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

`IDBKeyRange`

24

23-57

12

16

10-16

10

15

7

Yes

Yes

22

14

8

Yes

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

`includes`

52

≤18

47

No

39

10.1

52

52

Yes

41

10.3

6.0

`lower`

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

`lowerOpen`

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

`only`

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

`upper`

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

`upperBound`

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

See also
--------

-   [Using IndexedDB](indexeddb_api/using_indexeddb)
-   Starting transactions: [`IDBDatabase`](idbdatabase)
-   Using transactions: [`IDBTransaction`](idbtransaction)
-   Setting a range of keys: [`IDBKeyRange`](idbkeyrange)
-   Retrieving and making changes to your data: [`IDBObjectStore`](idbobjectstore)
-   Using cursors: [`IDBCursor`](idbcursor)
-   Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBKeyRange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBKeyRange</a>
