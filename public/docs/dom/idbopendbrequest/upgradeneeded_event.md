IDBOpenDBRequest: upgradeneeded event
=====================================

The `upgradeneeded` event is fired when an attempt was made to open a database with a version number higher than its current version.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../idbversionchangeevent"><code>IDBVersionChangeEvent</code></a></td></tr><tr class="even"><td>Event handler</td><td><a href="onupgradeneeded"><code>onupgradeneeded</code></a></td></tr></tbody></table>

Examples
--------

This example opens a database and handles the `upgradeneeded` event by making any necessary updates to the object store.

    // Open the database
    const dBOpenRequest = window.indexedDB.open('toDoList', 4);

    dBOpenRequest.addEventListener('upgradeneeded', event => {
      const db = event.target.result;
      console.log(`Upgrading to version ${db.version}`);

      // Create an objectStore for this database
      var objectStore = db.createObjectStore('toDoList', { keyPath: 'taskTitle' });

      // define what data items the objectStore will contain
      objectStore.createIndex('hours', 'hours', { unique: false });
      objectStore.createIndex('minutes', 'minutes', { unique: false });
      objectStore.createIndex('day', 'day', { unique: false });
      objectStore.createIndex('month', 'month', { unique: false });
      objectStore.createIndex('year', 'year', { unique: false });
    });

This is the same example, but uses the onupgradeneeded event handler property.

    // Open the database
    const dBOpenRequest = window.indexedDB.open('toDoList', 4);

    dBOpenRequest.onupgradeneeded = event => {
      const db = event.target.result;
      console.log(`Upgrading to version ${db.version}`);

      // Create an objectStore for this database
      var objectStore = db.createObjectStore('toDoList', { keyPath: 'taskTitle' });

      // define what data items the objectStore will contain
      objectStore.createIndex('hours', 'hours', { unique: false });
      objectStore.createIndex('minutes', 'minutes', { unique: false });
      objectStore.createIndex('day', 'day', { unique: false });
      objectStore.createIndex('month', 'month', { unique: false });
      objectStore.createIndex('year', 'year', { unique: false });
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

`upgradeneeded_event`

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
-   [`onupgradeneeded`](onupgradeneeded) event handler property

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBOpenDBRequest/upgradeneeded_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBOpenDBRequest/upgradeneeded_event</a>
