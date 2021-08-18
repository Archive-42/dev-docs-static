# IDBCursor.continuePrimaryKey()

The `continuePrimaryKey()` method of the [`IDBCursor`](../idbcursor) interface advances the cursor to the to the item whose key matches the key parameter as well as whose primary key matches the primary key parameter.

A typical use case, is to resume the iteration where a previous cursor has been closed, without having to compare the keys one by one.

Calling this method more than once before new cursor data has been loaded - for example, calling `continuePrimaryKey()` twice from the same onsuccess handler - results in an `InvalidStateError` being thrown on the second call because the cursor’s got value flag has been unset.

This method is only valid for cursors coming from an index. Using it for cursors coming from an object store will throw an error.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    cursor.continuePrimaryKey(key, primaryKey);

### Parameters

`key`  
The key to position the cursor at.

`primaryKey`  
The primary key to position the cursor at.

### Exceptions

This method may raise a [`DOMException`](../domexception) of one of the following types:

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>TransactionInactiveError</code></td><td>This IDBCursor's transaction is inactive.</td></tr><tr class="even"><td><code>DataError</code></td><td><p>The key parameter may have any of the following conditions:</p><ul><li>The key is not a valid key.</li><li>The key is less than or equal to this cursor's position and the cursor's direction is <code>next</code> or <code>nextunique</code>.</li><li>The key is greater than or equal to this cursor's position and this cursor's direction is <code>prev</code> or <code>prevunique</code>.</li></ul></td></tr><tr class="odd"><td><code>InvalidStateError</code></td><td>The cursor is currently being iterated or has iterated past its end.</td></tr><tr class="even"><td><code>InvalidAccessError</code></td><td>The cursor's direction is not <code>prev</code> or <code>next</code>.</td></tr></tbody></table>

## Example

here’s how you can resume an iteration of all articles tagged with `"javascript"` since your last visit:

    let request = articleStore.index("tag").openCursor();
    let count = 0;
    let unreadList = [];
    request.onsuccess = (event) => {
        let cursor = event.target.result;
        if (!cursor) { return; }
        let lastPrimaryKey = getLastIteratedArticleId();
        if (lastPrimaryKey > cursor.primaryKey) {
          cursor.continuePrimaryKey("javascript", lastPrimaryKey);
          return;
        }
        // update lastIteratedArticleId
        setLastIteratedArticleId(cursor.primaryKey);
        // preload 5 articles into the unread list;
        unreadList.push(cursor.value);
        if (++count < 5) {
          cursor.continue();
        }
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbcursor-continueprimarykey">Indexed Database API 2.0<br />
<span class="small">The definition of 'continuePrimaryKey()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`continuePrimaryKey`

58

79

10

No

45

10.1

58

58

51

43

10.3

7.0

## See also

- [Using IndexedDB](../indexeddb_api/using_indexeddb)
- Starting transactions: [`IDBDatabase`](../idbdatabase)
- Using transactions: [`IDBTransaction`](../idbtransaction)
- Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
- Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
- Using cursors: [`IDBCursor`](../idbcursor)
- Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBCursor/continuePrimaryKey" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBCursor/continuePrimaryKey</a>
