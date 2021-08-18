# IDBDatabaseSync

**Draft**

This page is not complete.

**Important**: The synchronous version of the IndexedDB API was originally intended for use only with [Web Workers](web_workers_api/using_web_workers), and was eventually removed from the spec because its need was questionable. It may however be reintroduced in the future if there is enough demand from web developers.

The `DatabaseSync` interface in the [IndexedDB API](indexeddb_api) represents a synchronous [connection to a database](indexeddb_api#gloss_database_connection).

## Method overview

<table><tbody><tr class="odd"><td><code>IDBObjectStoreSync createObjectStore (in DOMString name, in DOMString keypath, in optional boolean autoIncrement) raises (IDBDatabaseException); </code></td></tr><tr class="even"><td><code>IDBObjectStoreSync openObjectStore (in DOMString name, in optional unsigned short mode) raises (IDBDatabaseException);</code></td></tr><tr class="odd"><td><code>void removeObjectStore (in DOMString storeName) raises (IDBDatabaseException);</code></td></tr><tr class="even"><td><code>void setVersion (in DOMString version);</code></td></tr><tr class="odd"><td><code>IDBTransactionSync transaction (in optional DOMStringList storeNames, in optional unsigned int timeout) raises (IDBDatabaseException);</code></td></tr></tbody></table>

## Attributes

<table><thead><tr class="header"><th>Attribute</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>description</code></td><td><code>readonly DOMString </code></td><td>The human-readable description of the connected database.</td></tr><tr class="even"><td><code>name </code></td><td><code>readonly DOMString </code></td><td>The name of the connected database.</td></tr><tr class="odd"><td><code>objectStores </code></td><td><code>readonly DOMStringList </code></td><td>The names of the object stores that exist in the connected database.</td></tr><tr class="even"><td><code>version </code></td><td><code>readonly DOMString</code></td><td>The version of the connected database. Has the null value when the database is first created.</td></tr></tbody></table>

## Methods

### createObjectStore()

Creates and returns a new object store with the given name in the connected database.

     IDBObjectStoreSync createObjectStore(
      in DOMString name,
      in DOMString keypath,
      in optional boolean autoIncrement
    ) raises  (IDBDatabaseException);

##### Parameters

name  
The name of a new object store.

keypath  
The [key path](indexeddb_api#gloss_key_path) used by the new object store. If a null path is specified, then the object store does not have a key path, and uses out-of-line keys.

autoIncrement  
If true, the object store uses a [key generator](indexeddb_api#gloss_key_generator); if false, it does not use one.

##### Returns

[`IDBObjectStoreSync`](idbobjectstoresync)  
An object to access the newly created object store.

##### Exceptions

This method can raise an IDBDatabaseException with the following code:

`CONSTRAINT_ERR`  
If an object store with the same name (based on case-sensitive comparison) already exists in the connected database.

### openObjectStore()

Opens the object store with the given name in the connected database using the specified mode.

    IDBObjectStoreSync openObjectStore (
      in DOMString name,
      in optional unsigned short mode
    ) raises (IDBDatabaseException);

##### Parameters

name  
The name of the object store to open.

mode  
The mode that is used to access the object store.

##### Returns

[`IDBObjectStoreSync`](idbobjectstoresync)  
An object to access the opened object store.

##### Exceptions

This method can raise an IDBDatabaseException with the following code:

`NOT_FOUND_ERR`  
If an object store with the given name (based on case-sensitive comparison) already exists in the connected database.

### removeObjectStore()

Destroys an object store with the given name, as well as all indexes that reference that object store.

    void removeObjectStore (
      in DOMString storeName
    ) raises (IDBDatabaseException);

##### Parameters

storeName  
The name of an existing object store to remove.

##### Returns

`void`

##### Exceptions

This method can raise an IDBDatabaseException with the following code:

`NOT_FOUND_ERR`  
If the object store with the given name (based on case-sensitive comparison) does not exist in the connected database.

### setVersion()

Sets the version of the connected database.

    void setVersion (
      in DOMString version
    );

##### Parameters

##### Returns

`void`

version  
The version to store in the database.

### transaction()

Creates and returns a transaction, acquiring locks on the given database objects, within the specified timeout duration, if possible.

    IDBTransactionSync transaction (
      in optional DOMStringList storeNames,
      in optional unsigned int timeout
    ) raises (IDBDatabaseException);

##### Parameters

storeNames  
The names of object stores and indexes in the scope of the new transaction.

timeout  
The interval that this operation is allowed to take to acquire locks on all the objects stores and indexes identified in `storeNames`.

##### Returns

`IDBTransactionSync`  
An object to access the newly created transaction.

##### Exceptions

This method can raise an IDBDatabaseException with the following code:

`TIMEOUT_ERR`  
If reserving all the database objects identified in `storeNames` takes longer than the `timeout` interval.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabaseSync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabaseSync</a>
