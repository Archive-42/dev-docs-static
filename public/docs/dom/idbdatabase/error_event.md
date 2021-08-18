# IDBDatabase: error event

The `error` event is fired on `IDBDatabase` when a request returns an error and the event bubbles up to the connection object.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onerror</code></td></tr></tbody></table>

## Examples

This example opens a database and tries to add a record, listening for the `error` event for the `add()` operation (this will occur if, for example, a record with the given `taskTitle` already exists):

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
      const newItem = { taskTitle: 'my task', hours: 10, minutes: 10, day: 10, month: 'January', year: 2020 };
      const db = dBOpenRequest.result;

      db.addEventListener('error', () => {
        console.log(`Error adding new item: ${newItem.taskTitle}`);
      });

      // open a read/write db transaction, ready for adding the data
      const transaction = db.transaction(['toDoList'], 'readwrite');
      const objectStore = transaction.objectStore('toDoList');
      const objectStoreRequest = objectStore.add(newItem);
    };

The same example, using the `onerror` property instead of `addEventListener()`:

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
      const newItem = { taskTitle: 'my task', hours: 10, minutes: 10, day: 10, month: 'January', year: 2020 };
      const db = dBOpenRequest.result;

      db.onerror = () => {
        console.log(`Error adding new item: ${newItem.taskTitle}`);
      };

      // open a read/write db transaction, ready for adding the data
      const transaction = db.transaction(['toDoList'], 'readwrite');
      const objectStore = transaction.objectStore('toDoList');
      const objectStoreRequest = objectStore.add(newItem);
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

`error_event`

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
- `onerror` event handler property

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/error_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/error_event</a>
