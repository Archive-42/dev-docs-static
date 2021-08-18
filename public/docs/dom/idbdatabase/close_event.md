# IDBDatabase: close event

The `close` event is fired on `IDBDatabase` when the database connection is unexpectedly closed. This could happen, for example, if the underlying storage is removed or if the user clears the database in the browser's history preferences.

Note that it is not fired if the database connection is closed normally using `IDBDatabase.close()`.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onerror</code></td></tr></tbody></table>

## Examples

This example opens a database and listens for the `close` event:

    // Open the database
    const dBOpenRequest = window.indexedDB.open('toDoList', 4);

    dBOpenRequest.onupgradeneeded = (event) => {
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

    dBOpenRequest.onsuccess = (event) => {

      const db = dBOpenRequest.result;
      db.addEventListener('close', () => {
        console.log('Database connection closed');
      });

    };

The same example, using the `onclose` property instead of `addEventListener()`:

    // Open the database
    const dBOpenRequest = window.indexedDB.open('toDoList', 4);

    dBOpenRequest.onupgradeneeded = (event) => {
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

    dBOpenRequest.onsuccess = (event) => {

      const db = dBOpenRequest.result;
      db.onclose = () => {
        console.log('Database connection closed');
      };

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

`close_event`

31

≤18

50

?

Yes

10.1

≤37

31

50

Yes

10.3

2.0

## See also

- [Using IndexedDB](../indexeddb_api/using_indexeddb)
- `onclose` event handler property

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/close_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/close_event</a>
