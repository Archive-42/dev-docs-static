IDBDatabase: versionchange event
================================

The `versionchange` event is fired when a database structure change ([`IDBOpenDBRequest.onupgradeneeded`](../idbopendbrequest/onupgradeneeded) event or [`IDBFactory.deleteDatabase`](../idbfactory/deletedatabase)) was requested.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onversionchange"><code>onversionchange</code></a></td></tr></tbody></table>

Examples
--------

This example opens a database and, on success, adds a listener to `versionchange`:

    // Open the database
    const dBOpenRequest = window.indexedDB.open('Nonexistent', 4);

    dBOpenRequest.onupgradeneeded = event => {
      const db = event.target.result;
      // Create an objectStore for this database
      const objectStore = db.createObjectStore('toDoList', { keyPath: 'taskTitle' });

      // define what data items the objectStore will contain
      objectStore.createIndex('hours', 'hours', { unique: false });
      objectStore.createIndex('minutes', 'minutes', { unique: false });
      objectStore.createIndex('day', 'day', { unique: false });
      objectStore.createIndex('month', 'month', { unique: false });
      objectStore.createIndex('year', 'year', { unique: false });
    };

    dBOpenRequest.addEventListener('success', event => {
      const db = event.target.result;
      db.addEventListener('versionchange', event => {
        console.log('The version of this database has changed');
      });

    });

The same example, using the `onversionchange` event handler property:

    // Open the database
    const dBOpenRequest = window.indexedDB.open('Nonexistent', 4);

    dBOpenRequest.onupgradeneeded = event => {
      const db = event.target.result;
      // Create an objectStore for this database
      const objectStore = db.createObjectStore('toDoList', { keyPath: 'taskTitle' });

      // define what data items the objectStore will contain
      objectStore.createIndex('hours', 'hours', { unique: false });
      objectStore.createIndex('minutes', 'minutes', { unique: false });
      objectStore.createIndex('day', 'day', { unique: false });
      objectStore.createIndex('month', 'month', { unique: false });
      objectStore.createIndex('year', 'year', { unique: false });
    };

    dBOpenRequest.onsuccess = event => {
      const db = event.target.result;
      db.onversionchange = event => {
        console.log('The version of this database has changed');
      };

    };

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

`versionchange_event`

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

See also
--------

-   [Using IndexedDB](../indexeddb_api/using_indexeddb)
-   [`onversionchange`](onversionchange) event handler property

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/versionchange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/versionchange_event</a>
