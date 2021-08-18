# IDBDatabase: abort event

The `abort` event is fired on `IDBDatabase` when a transaction is aborted and bubbles up to the connection object.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onabort</code></td></tr></tbody></table>

## Examples

This example opens a database (creating the database if it does not exist), then opens a transaction, adds a listener to the `abort` event, then aborts the transaction to trigger the event.

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

      db.addEventListener('abort', () => {
        console.log('Transaction aborted');
      });

      // open a read/write db transaction, ready for adding the data
      const transaction = db.transaction(['toDoList'], 'readwrite');

      // abort the transaction
      transaction.abort();
    };

The same example, but assigning the event handler to the `onabort` property:

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

      db.onabort = () => {
        console.log('Transaction aborted');
      };

      // open a read/write db transaction, ready for adding the data
      const transaction = db.transaction(['toDoList'], 'readwrite');

      // abort the transaction
      transaction.abort();
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

`abort_event`

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
- `onabort` event handler property

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/abort_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/abort_event</a>
