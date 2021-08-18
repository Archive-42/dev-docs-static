# IDBRequest: success event

The `success` event is fired when an `IDBRequest` succeeds.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onsuccess</code></td></tr></tbody></table>

## Examples

This example tries to open a database and listens for the `success` event using `addEventListener()`:

    // Open the database
    const openRequest = window.indexedDB.open('toDoList', 4);

    openRequest.onupgradeneeded = (event) => {
      const db = event.target.result;

      db.onerror = () => {
        console.log('Error creating database');
      };

      // Create an objectStore for this database
      var objectStore = db.createObjectStore('toDoList', { keyPath: 'taskTitle' });

      // define what data items the objectStore will contain
      objectStore.createIndex('hours', 'hours', { unique: false });
      objectStore.createIndex('minutes', 'minutes', { unique: false });
      objectStore.createIndex('day', 'day', { unique: false });
      objectStore.createIndex('month', 'month', { unique: false });
      objectStore.createIndex('year', 'year', { unique: false });
    };

    openRequest.addEventListener('success', (event) => {
      console.log('Database opened successfully!');
    });

The same example, but using the `onsuccess` event handler property:

    // Open the database
    const openRequest = window.indexedDB.open('toDoList', 4);

    openRequest.onupgradeneeded = (event) => {
      const db = event.target.result;

      db.onerror = () => {
        console.log('Error creating database');
      };

      // Create an objectStore for this database
      var objectStore = db.createObjectStore('toDoList', { keyPath: 'taskTitle' });

      // define what data items the objectStore will contain
      objectStore.createIndex('hours', 'hours', { unique: false });
      objectStore.createIndex('minutes', 'minutes', { unique: false });
      objectStore.createIndex('day', 'day', { unique: false });
      objectStore.createIndex('month', 'month', { unique: false });
      objectStore.createIndex('year', 'year', { unique: false });
    };

    openRequest.onsuccess = (event) => {
      console.log('Database opened successfully!');
    };

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

`success_event`

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
- `onsuccess` event handler property

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBRequest/success_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBRequest/success_event</a>
