IDBTransaction: complete event
==============================

The `complete` handler is executed when a transaction successfully completed.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="oncomplete"><code>oncomplete</code></a></td></tr></tbody></table>

Examples
--------

Using [`addEventListener()`](../eventtarget/addeventlistener):

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

      // add a listener for `complete`
      transaction.addEventListener('complete', event => {
        console.log('Transaction was competed');
      });

      const objectStore = transaction.objectStore('toDoList');
      const newItem = { taskTitle: 'my task', hours: 10, minutes: 10, day: 10, month: 'January', year: 2019 };
      const objectStoreRequest = objectStore.add(newItem);
    };

Using the [`oncomplete`](oncomplete) property:

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

      // add a listener for `complete`
      transaction.oncomplete = event => {
        console.log('Transaction was competed');
      };

      const objectStore = transaction.objectStore('toDoList');
      const newItem = { taskTitle: 'my task', hours: 10, minutes: 10, day: 10, month: 'January', year: 2019 };
      const objectStoreRequest = objectStore.add(newItem);
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

`complete_event`

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

See also
--------

-   [Using IndexedDB](../indexeddb_api/using_indexeddb)
-   [`oncomplete`](oncomplete) event handler property

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBTransaction/complete_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBTransaction/complete_event</a>
