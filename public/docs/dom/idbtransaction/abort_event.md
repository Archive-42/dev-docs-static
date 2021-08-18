# IDBTransaction: abort event

The `abort` event is fired when an `IndexedDB` transaction is aborted.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onabort"><code>onabort</code></a></td></tr></tbody></table>

This can happen for any of the following reasons:

- bad requests, (for example, trying to add the same key twice, or put the same index key when the key has a uniqueness constraint),
- an explicit [`abort()`](abort) call
- an uncaught exception in the request's success/error handler,
- an I/O error (an actual failure to write to disk, for example disk detached, or other OS/hardware failure)
- quota exceeded.

## Examples

This example opens a database (creating the database if it does not exist), then opens a transaction, adds a listener to the `abort` event, then aborts the transaction to trigger the event.

    // Open the database
    const DBOpenRequest = window.indexedDB.open('toDoList', 4);

    DBOpenRequest.onupgradeneeded = event => {
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

    DBOpenRequest.onsuccess = event => {
      const db = DBOpenRequest.result;

      // open a read/write db transaction, ready for adding the data
      const transaction = db.transaction(['toDoList'], 'readwrite');

      // add a listener for `abort`
      transaction.addEventListener('abort', () => {
        console.log('Transaction was aborted');
      });

      // abort the transaction
      transaction.abort();
    };

The same example, but assigning the event handler to the [`onabort`](onabort) property:

    // Open the database
    const DBOpenRequest = window.indexedDB.open('toDoList', 4);

    DBOpenRequest.onupgradeneeded = event => {
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

    DBOpenRequest.onsuccess = event => {
      const db = DBOpenRequest.result;

      // open a read/write db transaction, ready for adding the data
      const transaction = db.transaction(['toDoList'], 'readwrite');

      // add a listener for `abort`
      transaction.onabort = (event) => {
        console.log('Transaction was aborted');
      };

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

Yes

Yes

22

14

8

Yes

## See also

- [Using IndexedDB](../indexeddb_api/using_indexeddb)
- [`onabort`](onabort) event handler property

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBTransaction/abort_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBTransaction/abort_event</a>
