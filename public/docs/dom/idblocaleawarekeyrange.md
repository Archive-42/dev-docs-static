IDBLocaleAwareKeyRange
======================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `IDBLocaleAwareKeyRange` interface of the [IndexedDB API](indexeddb_api) is a Firefox-specific version of [`IDBKeyRange`](idbkeyrange) — it functions in exactly the same fashion, and has the same properties and methods, but it is intended for use with [`IDBIndex`](idbindex) objects when the original index had a `locale` value specified upon its creation (see [`createIndex()`'s optionalParameters](idbobjectstore/createindex#parameters)) — that is, it has [locale aware sorting](indexeddb_api/using_indexeddb#locale-aware_sorting) enabled.

Methods
-------

*This interface inherits all the methods of its parent interface, [`IDBKeyRange`](idbkeyrange).*

Properties
----------

*This interface inherits all the properties of its parent interface, [`IDBKeyRange`](idbkeyrange).*

Bear in mind however that `IDBLocaleAwareKeyRange` has its own implementation of [`IDBKeyRange.bound`](idbkeyrange/bound). This is because when you use `bound()`, it checks if lower bound &lt; upper bound, and throws an exception if that’s not the case. With locale-aware indexes, the meaning of &lt; depends on the locale, so for example in Lithuanian Y is sorted between I and K. The only difference between `IDBKeyRange` and `IDBLocaleAwareKeyRange` is that the latter doesn’t do the aforementioned check.

Developers should always use `IDBLocaleAwareKeyRange` when dealing with locale-aware indexes.

Examples
--------

    function displayData() {
      var keyRangeValue = IDBLocaleAwareKeyRange.bound("A", "F");

      var transaction = db.transaction(['fThings'], 'readonly');
      var objectStore = transaction.objectStore('fThings');

      var myIndex = objectStore.index('lName');
      myIndex.openCursor(keyRangeValue).onsuccess = function(event) {
        var cursor = event.target.result;
        if(cursor) {
          var tableRow = document.createElement('tr');
          tableRow.innerHTML =   '&lt;td&gt;' + cursor.value.id + '&lt;/td&gt;'
                               + '&lt;td&gt;' + cursor.value.lName + '&lt;/td&gt;'
                               + '&lt;td&gt;' + cursor.value.fName + '&lt;/td&gt;'
                               + '&lt;td&gt;' + cursor.value.jTitle + '&lt;/td&gt;'
                               + '&lt;td&gt;' + cursor.value.company + '&lt;/td&gt;'
                               + '&lt;td&gt;' + cursor.value.eMail + '&lt;/td&gt;'
                               + '&lt;td&gt;' + cursor.value.phone + '&lt;/td&gt;'
                               + '&lt;td&gt;' + cursor.value.age + '&lt;/td&gt;';
          tableEntry.appendChild(tableRow);

          cursor.continue();
        } else {
          console.log('Entries all displayed.');
        }
      };
    };

Specifications
--------------

Not currently part of any specification.

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

`IDBLocaleAwareKeyRange`

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

See also
--------

-   [Using IndexedDB](indexeddb_api/using_indexeddb)
-   Starting transactions: [`IDBDatabase`](idbdatabase)
-   Using transactions: [`IDBTransaction`](idbtransaction)
-   Setting a range of keys: [`IDBKeyRange`](idbkeyrange)
-   Retrieving and making changes to your data: [`IDBObjectStore`](idbobjectstore)
-   Using cursors: [`IDBCursor`](idbcursor)
-   Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBLocaleAwareKeyRange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBLocaleAwareKeyRange</a>
