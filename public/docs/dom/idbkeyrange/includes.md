IDBKeyRange.includes()
======================

The `includes()` method of the [`IDBKeyRange`](../idbkeyrange) interface returns a boolean indicating whether a specified key is inside the key range.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var isIncluded = myKeyRange.includes(key)

### Parameters

*key* The key you want to check for in your key range. This can be any type.

### Return value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

### Exceptions

This method may raise a [`DOMException`](../domexception) of the following type:

Attribute

Description

[`DataError`](../domerror)

The supplied key was not a valid key.

Example
-------

    var keyRangeValue = IDBKeyRange.bound('A', 'K', false, false);

    var myResult = keyRangeValue.includes('F');
    // Returns true

    var myResult = keyRangeValue.includes('W');
    // Returns false

Polyfill
--------

The `includes()` method was added in the second edition of the Indexed DB specification. For browsers that do not support it, the following polyfill can be used.

    IDBKeyRange.prototype.includes = IDBKeyRange.prototype.includes || function(key) {
      var r = this, c;
      if (r.lower !== undefined) {
        c = indexedDB.cmp(key, r.lower);
        if (r.lowerOpen && c <= 0) return false;
        if (!r.lowerOpen && c < 0) return false;
      }
      if (r.upper !== undefined) {
        c = indexedDB.cmp(key, r.upper);
        if (r.upperOpen && c >= 0) return false;
        if (!r.upperOpen && c > 0) return false;
      }
      return true;
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbkeyrange-includes">Indexed Database API 2.0<br />
<span class="small">The definition of 'includes()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbkeyrange-includes">Indexed Database API 2.0<br />
<span class="small">The definition of 'includes()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

See also
--------

-   [Using IndexedDB](../indexeddb_api/using_indexeddb)
-   Starting transactions: [`IDBDatabase`](../idbdatabase)
-   Using transactions: [`IDBTransaction`](../idbtransaction)
-   Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
-   Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
-   Using cursors: [`IDBCursor`](../idbcursor)
-   Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBKeyRange/includes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBKeyRange/includes</a>
