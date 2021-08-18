# IDBFactory.cmp()

The `cmp()` method of the [`IDBFactory`](../idbfactory) interface compares two values as keys to determine equality and ordering for IndexedDB operations, such as storing and iterating.

**Note:** This feature is available in [Web Workers](../web_workers_api).

**Note**: Do not use this method for comparing arbitrary JavaScript values, because many JavaScript values are either not valid IndexedDB keys (booleans and objects, for example) or are treated as equivalent IndexedDB keys (for example, since IndexedDB ignores arrays with non-numeric properties and treats them as empty arrays, so any non-numeric arrays are treated as equivalent). This throws an exception if either of the values is not a valid key.

## Syntax

    var result = indexedDB.cmp(first, second);

### Parameters

first  
The first key to compare.

second  
The second key to compare.

### Return value

An integer that indicates the result of the comparison; the table below lists the possible values and their meanings:

<table><thead><tr class="header"><th>Returned value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td>-1</td><td>1st key is less than the 2nd key</td></tr><tr class="even"><td>0</td><td>1st key is equal to the 2nd key</td></tr><tr class="odd"><td>1</td><td>1st key is greater than the 2nd key</td></tr></tbody></table>

### Exceptions

This method may raise a [`DOMException`](../domexception) of the following types:

Attribute

Description

[`DataError`](../domerror)

One of the supplied keys was not a valid key.

## Example

    var a = 1;
    var b = 2;
    var result = window.indexedDB.cmp(a, b);
    console.log( "Comparison results: " + result );

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbfactory-cmp">Indexed Database API 2.0<br />
<span class="small">The definition of 'cmp()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbfactory-cmp">Indexed Database API 2.0<br />
<span class="small">The definition of 'cmp()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`cmp`

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

## See also

- [Using IndexedDB](../indexeddb_api/using_indexeddb)
- Starting transactions: [`IDBDatabase`](../idbdatabase)
- Using transactions: [`IDBTransaction`](../idbtransaction)
- Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
- Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
- Using cursors: [`IDBCursor`](../idbcursor)
- Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBFactory/cmp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBFactory/cmp</a>
