# IDBTransaction.objectStoreNames

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `objectStoreNames` read-only property of the [`IDBTransaction`](../idbtransaction) interface returns a [`DOMStringList`](../domstringlist) of names of [`IDBObjectStore`](../idbobjectstore) objects.

## Syntax

    var myDatabase = transactionObj.objectStoreNames;

### Returns

<span style="line-height: 1.5;">A </span> [`DOMStringList`](../domstringlist) of names of [`IDBObjectStore`](../idbobjectstore) objects.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbdatabase-objectstorenames">Indexed Database API 2.0<br />
<span class="small">The definition of 'ObjectStoreNames' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbtransaction-objectstorenames">Indexed Database API 2.0<br />
<span class="small">The definition of 'ObjectStoreNames' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`ObjectStoreNames`

48

≤79

Yes

No

35

Yes

48

48

Yes

35

Yes

5.0

## See also

- [Using IndexedDB](../indexeddb_api/using_indexeddb)
- Starting transactions: [`IDBDatabase`](../idbdatabase)
- Using transactions: [`IDBTransaction`](../idbtransaction)
- Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
- Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
- Using cursors: [`IDBCursor`](../idbcursor)
- Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBTransaction/ObjectStoreNames" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBTransaction/ObjectStoreNames</a>
