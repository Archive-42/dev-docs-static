# IDBOpenDBRequest: blocked event

The `blocked` handler is executed when an open connection to a database is blocking a `versionchange` transaction on the same database.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../idbversionchangeevent"><code>IDBVersionChangeEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onblocked"><code>onblocked</code></a></td></tr></tbody></table>

## Examples

Using `addEventListener()`:

    // Open the database
    const DBOpenRequest = window.indexedDB.open('toDoList', 4);

    DBOpenRequest.onupgradeneeded = (event) => {
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

    DBOpenRequest.onsuccess = (event) => {
      // Let's try to open the same database with a higher revision version
      const req2 = indexedDB.open('toDoList', 5);

      // In this case the onblocked handler will be executed
      req2.addEventListener('blocked', () => {
        console.log('Request was blocked');
      });

    };

Using the `onblocked` property:

    // Open the database
    const DBOpenRequest = window.indexedDB.open('toDoList', 4);

    DBOpenRequest.onupgradeneeded = (event) => {
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

    DBOpenRequest.onsuccess = (event) => {
      // Let's try to open the same database with a higher revision version
      const req2 = indexedDB.open('toDoList', 5);

      // In this case the onblocked handler will be executed
      req2.onblocked = () => {
        console.log('Request was blocked');
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

`blocked_event`

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
- [`onblocked`](onblocked) event handler property

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBOpenDBRequest/blocked_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBOpenDBRequest/blocked_event</a>
