# IDBDatabase.onversionchange

The `onversionchange` event handler of the [`IDBDatabase`](../idbdatabase) interface handles the versionchange event, fired when a database structure change ([`IDBOpenDBRequest.onupgradeneeded`](../idbopendbrequest/onupgradeneeded) event or [`IDBFactory.deleteDatabase`](../idbfactory/deletedatabase)) was requested elsewhere (most probably in another window/tab on the same computer).

This is different from the `versionchange` transaction (but it is related).

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    IDBDatabase.onversionchange = function(event) { ... }

## Example

This example shows an [`IDBOpenDBRequest.onupgradeneeded`](../idbopendbrequest/onupgradeneeded) block that creates a new object store; it also includes `onerror` and `onabort` functions to handle non-success cases, and an onversionchange function to notify when a database structure change has occurred.

    request.onupgradeneeded = function(event) {
      var db = event.target.result;

      db.onerror = function(event) {
        note.innerHTML += '<li>Error opening database.</li>';
      };

      db.onabort = function(event) {
        note.innerHTML += '<li>Database opening aborted!</li>';
      };

      // Create an objectStore for this database

      var objectStore = db.createObjectStore("toDoList", { keyPath: "taskTitle" });

      // define what data items the objectStore will contain

      objectStore.createIndex("hours", "hours", { unique: false });
      objectStore.createIndex("minutes", "minutes", { unique: false });
      objectStore.createIndex("day", "day", { unique: false });
      objectStore.createIndex("month", "month", { unique: false });
      objectStore.createIndex("year", "year", { unique: false });

      objectStore.createIndex("notified", "notified", { unique: false });

      note.innerHTML += '<li>Object store created.</li>';

      db.onversionchange = function(event) {
        note.innerHTML += '<li>a database change has occurred; you should refresh this
                           browser window, or close it down and use the other open version of
                           this application, wherever it exists.</li>';
      };
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbdatabase-onversionchange">Indexed Database API 2.0<br />
<span class="small">The definition of 'onversionchange' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbdatabase-onversionchange">Indexed Database API 2.0<br />
<span class="small">The definition of 'onversionchange' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`onversionchange`

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
- `versionchange` event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/onversionchange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/onversionchange</a>
