# IDBCursor.request

The `request` read-only property of the [`IDBCursor`](../idbcursor) interface returns the [`IDBRequest`](../idbrequest) used to obtain the cursor.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    IDBCursor.request;

### Value

An [`IDBRequest`](../idbrequest) object instance.

## Examples

When you open a cursor, the `request` property is then available on that cursor object, to tell you what request object the cursor originated from. For example:

    function displayData() {
      list.textContent = '';
      const transaction = db.transaction(['rushAlbumList'], 'readonly');
      const objectStore = transaction.objectStore('rushAlbumList');

      const request = objectStore.openCursor();

      request.onsuccess = function(event) {
        const cursor = event.target.result;
          if(cursor) {
            const listItem = document.createElement('li');
            listItem.innerHTML = '<strong>' + cursor.value.albumTitle + '</strong>, ' + cursor.value.year;
            list.appendChild(listItem);
            console.log(cursor.request);
            cursor.continue();
          } else {
            console.log('Entries all displayed.');
          }
      };
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/IndexedDB/#dom-idbcursor-request">Indexed Database API 3.0<br />
<span class="small">The definition of 'request' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- [Using IndexedDB](../indexeddb_api/using_indexeddb)
- Starting transactions: [`IDBDatabase`](../idbdatabase)
- Using transactions: [`IDBTransaction`](../idbtransaction)
- Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
- Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
- Using cursors: [`IDBCursor`](../idbcursor)
- Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBCursor/request" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBCursor/request</a>
