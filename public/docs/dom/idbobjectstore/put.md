# IDBObjectStore.put()

The `put()` method of the [`IDBObjectStore`](../idbobjectstore) interface updates a given record in a database, or inserts a new record if the given item does not already exist.

It returns an [`IDBRequest`](../idbrequest) object, and, in a separate thread, creates a [structured clone](https://www.whatwg.org/specs/web-apps/current-work/multipage/common-dom-interfaces.html#structured-clone) of the value and stores the cloned value in the object store. This is for adding new records, or updating existing records in an object store when the transaction's mode is `readwrite`. If the record is successfully stored, then a success event is fired on the returned request object with the `result` set to the key for the stored record, and the `transaction` set to the transaction in which this object store is opened.

The put method is an<span class="database"> _update or insert_ </span>method. See the [`IDBObjectStore.add`](add) method for an _insert only_ method.

Bear in mind that if you have a [`IDBCursor`](../idbcursor) to the record you want to update, updating it with [`IDBCursor.update()`](../idbcursor/update) is preferable to using [`IDBObjectStore.put()`](put). Doing so makes it clear that an existing record will be updated, instead of a new record being inserted.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    let request = objectStore.put(item);
    let request = objectStore.put(item, key);

### Parameters

item  
The item you wish to update (or insert).

key <span class="badge inline optional">Optional</span>  
The primary key of the record you want to update (e.g. from [`IDBCursor.primaryKey`](../idbcursor/primarykey)). This is only needed for object stores that have an `autoIncrement` primary key, therefore the key is not in a field on the record object. In such cases, calling `put(item)` will always insert a new record, because it doesn't know what existing record you might want to modify.

### Return value

An [`IDBRequest`](../idbrequest) object on which subsequent events related to this operation are fired.

### Exceptions

This method may raise a [`DOMException`](../domexception) of one of the following types:

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>ReadOnlyError</code></td><td>The transaction associated with this operation is in read-only <a href="../idbtransaction#mode_constants">mode</a>.</td></tr><tr class="even"><td><code>TransactionInactiveError</code></td><td>This <a href="../idbobjectstore"><code>IDBObjectStore</code></a>'s transaction is inactive.</td></tr><tr class="odd"><td><code>DataError</code></td><td><p>Any of the following conditions apply:</p><ul><li>The object store uses in-line keys or has a key generator, and a key parameter was provided.</li><li>The object store uses out-of-line keys and has no key generator, and no key parameter was provided.</li><li>The object store uses in-line keys but no key generator, and the object store's key path does not yield a valid key.</li><li>The key parameter was provided but does not contain a valid key.</li></ul></td></tr><tr class="even"><td><code>InvalidStateError</code></td><td>The <a href="../idbobjectstore"><code>IDBObjectStore</code></a> has been deleted or removed.</td></tr><tr class="odd"><td><code>DataCloneError</code></td><td>The data being stored could not be cloned by the internal structured cloning algorithm.<br />
</td></tr></tbody></table>

## Parameters

value  
The value to be stored.

key  
The key to use to identify the record. If unspecified, it results to null. If the object store has a key generator (e.g. autoincrement) the key of the object must be passed in to update the object.

## Example

The following example requests a given record title; when that request is successful the `onsuccess` function gets the associated record from the [`IDBObjectStore`](../idbobjectstore) (made available as `objectStoreTitleRequest.result`<span style="line-height: 1.5;">), updates one property of the record, and then puts the updated record back into the object store in another request with `put()`. For a full working example, see our </span>[To-do Notifications](https://github.com/mdn/to-do-notifications/)<span style="line-height: 1.5;"> app (</span>[view example live](https://mdn.github.io/to-do-notifications/)<span style="line-height: 1.5;">.)</span>

    const title = "Walk dog";

    // Open up a transaction as usual
    const objectStore = db.transaction(['toDoList'], "readwrite").objectStore('toDoList');

    // Get the to-do list object that has this title as it's title
    const objectStoreTitleRequest = objectStore.get(title);

    objectStoreTitleRequest.onsuccess = () => {
      // Grab the data object returned as the result
      const data = objectStoreTitleRequest.result;

      // Update the notified value in the object to "yes"
      data.notified = "yes";

      // Create another request that inserts the item back into the database
      const updateTitleRequest = objectStore.put(data);

      // Log the transaction that originated this request
      console.log("The transaction that originated this request is " + updateTitleRequest.transaction);

      // When this new request succeeds, run the displayData() function again to update the display
      updateTitleRequest.onsuccess = () => {
        displayData();
      };
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbobjectstore-put">Indexed Database API 2.0<br />
<span class="small">The definition of 'put()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbobjectstore-put">Indexed Database API 2.0<br />
<span class="small">The definition of 'put()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`put`

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
- Starting transactions: [`IDBDatabase`](../idbdatabase)
- Using transactions: [`IDBTransaction`](../idbtransaction)
- Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
- Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
- Using cursors: [`IDBCursor`](../idbcursor)
- Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/put" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBObjectStore/put</a>
