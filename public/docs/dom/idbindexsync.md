IDBIndexSync
============

**Draft**

This page is not complete.

**Important**: The synchronous version of the IndexedDB API was originally intended for use only with [Web Workers](web_workers_api/using_web_workers), and was eventually removed from the spec because its need was questionable. It may however be reintroduced in the future if there is enough demand from web developers.

The `IDBIndexSync` interface of the [IndexedDB API](indexeddb_api) provides synchronous access to an [index](indexeddb_api#gloss_index) in a database.

Method overview
---------------

<table><tbody><tr class="odd"><td><code>any add (in any value, in optional any key) raises (IDBDatabaseException);</code></td></tr><tr class="even"><td><code>any get (in any key) raises (IDBDatabaseException);</code></td></tr><tr class="odd"><td><code>any getObject (in any key) raises (IDBDatabaseException);</code></td></tr><tr class="even"><td><code>void openCursor (in optional IDBKeyRange range, in optional unsigned short direction) raises (IDBDatabaseException);</code></td></tr><tr class="odd"><td><code>void openObjectCursor (in optional IDBKeyRange range, in optional unsigned short direction) raises (IDBDatabaseException);</code></td></tr><tr class="even"><td><code>any put (in any value, in optional any key) raises (IDBDatabaseException);</code></td></tr><tr class="odd"><td><code>void remove (in any key) raises (IDBDatabaseException);</code></td></tr></tbody></table>

Attributes
----------

<table><thead><tr class="header"><th>Attribute</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>keyPath</code></td><td><code>readonly DOMString</code></td><td>The <a href="indexeddb_api#gloss_key_path">key path</a> of this index. If this attribute is null, this index is not <a href="indexeddb_api#gloss_auto-populated">auto-populated</a>.</td></tr><tr class="even"><td><code>name</code></td><td><code>readonly DOMString</code></td><td>The name of this index.</td></tr><tr class="odd"><td><code>storeName</code></td><td><code>readonly DOMString</code></td><td>This index's <a href="indexeddb_api#gloss_referenced_object_store">referenced object store</a>.</td></tr><tr class="even"><td><code>unique</code></td><td><code>readonly boolean</code></td><td>If true, a key can have only one value within the index; if false, a key can have duplicate values.</td></tr></tbody></table>

Methods
-------

### add()

Stores the given value into this index, optionally with the specified key. If a record already exists with the given key, an exception is raised.

    any add(
      in any value,
      in optional any key
    ) raises (IDBDatabaseException);

##### Parameters

##### Returns

##### Exceptions

This method can raise a IDBDatabaseException with the following code:

value  
The value to store into the index.

key  
A key to use for identifying the record.

`any`  
The key for the stored record.

[`CONSTRAINT_ERR`](idbdatabaseexception#constraint_err)  
If a record exists in this index with a key corresponding to the *key* parameter or the index is auto-populated, or if no record exists with a key corresponding to the *value* parameter in the index's referenced object store.

### get()

Retrieves the value from this index for the record that corresponds to the given key.

    any get (
      in any key
    ) raises (IDBDatabaseException);

##### Parameters

key  
The key that identifies the record to be retrieved.

##### Returns

`any`  
The retrieved value from the index.

##### Exceptions

This method can raise an IDBDatabaseException with the following code:

`NOT_FOUND_ERR`  
If no record exists in this index for the given key.

### getObject()

Retrieves and returns the value from this index's referenced object store that corresponds to the given key.

    any getObject (
      in any key
    ) raises (IDBDatabaseException);

##### Parameters

key  
The key that identifies the record to be retrieved.

##### Returns

`any`  
The retrieved value from the referenced object store.

##### Exceptions

This method can raise a IDBDatabaseException with the following code:

`NOT_FOUND_ERR`  
If no record exists in this index for the given key.

### openCursor()

Creates a [cursor](indexeddb_api#gloss_cursor) over the records of this index. The range of the new cursor matches the specified [key range](indexeddb_api#gloss_key_range); if the key range is not specified or is null, then the range includes all the records.

    void openCursor (
      in optional IDBKeyRange range,
      in optional unsigned short direction
    ) raises (IDBDatabaseException);

##### Parameters

range  
The key range to use as the cursor's range.

direction  
The cursor's required direction.

##### Returns

`void`

##### Exceptions

This method can raise an IDBDatabaseException with the following code:

`NOT_FOUND_ERR`  
If no records exist in this index for the requested key range.

### openObjectCursor()

Creates a cursor over the records of this index's referenced object store, as arranged by this index. The range of the new cursor matches the specified key range; if the key range is not specified or is null, then the range includes all the records.

    void openObjectCursor (
      in optional IDBKeyRange range,
      in optional unsigned short direction
    ) raises (IDBDatabaseException);

##### Parameters

range  
The key range to use as the cursor's range.

direction  
The cursor's required direction.

##### Returns

`void`

##### Exceptions

This method can raise an IDBDatabaseException with the following code:

`NOT_FOUND_ERR`  
If no records exist in this index for the requested key range.

### put()

Stores the given value in this index and returns the key for the stored record. If a record already exists with the given key, the record is overwritten.

    any put (
      in any value,
      in optional any key) raises (IDBDatabaseException);

##### Parameters

value  
The value to be stored in the record.

key  
The key to be used to identify the record.

##### Returns

any  
The key for the stored record.

### remove()

Removes from this index any records that correspond to the given key.

    void remove (
      in any key
    ) raises (IDBDatabaseException);

##### Parameters

key  
Key of the records to be removed.

##### Exceptions

This method can raise a DatabaseException with the following code:

`NOT_FOUND_ERR`  
If a record does not exist in this index with the given key.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBIndexSync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBIndexSync</a>
