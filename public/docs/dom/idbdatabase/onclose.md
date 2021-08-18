IDBDatabase.onclose
===================

The `onclose` event handler of the [`IDBDatabase`](../idbdatabase) interface handles the `close` event, which is fired when the database is unexpectedly closed. This can happen, for example, when the application is shut down or access to the disk the database is stored on is lost while the database is open.

The `close` event is fired after all transactions have been aborted and the connection has been closed.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    IDBDatabase.onclose = function(event) { ... };

### Value

A function which is called when the `close` event is fired.

Example
-------

    db.onclose = function(event) {
      myAppShowAlert('The database "' + db.name + '" has unexpectedly closed.');
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbdatabase-onclose">Indexed Database API 2.0<br />
<span class="small">The definition of 'onclose' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`onclose`

31

approx

≤18

50

No

Yes

10.1

≤37

31

50

Yes

10.3

2.0

See also
--------

-   [Using IndexedDB](../indexeddb_api/using_indexeddb)
-   [`IDBDatabase`](../idbdatabase)
-   [close](close_event) event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/onclose" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabase/onclose</a>
