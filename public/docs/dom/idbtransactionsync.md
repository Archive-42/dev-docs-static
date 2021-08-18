IDBTransactionSync
==================

**Draft**

This page is not complete.

**Important**: The synchronous version of the IndexedDB API was originally intended for use only with [Web Workers](web_workers_api/using_web_workers), and was eventually removed from the spec because its need was questionable. It may however be reintroduced in the future if there is enough demand from web developers.

The `IDBTransactionSync` interface of the [IndexedDB API](indexeddb_api) provides a synchronous [transaction](indexeddb_api#gloss_transaction) on a database. When an application creates an IDBTransactionSync object, it blocks until the browser is able to reserve the require database objects.

Method overview
---------------

<table><tbody><tr class="odd"><td><code>void abort() raises (IDBDatabaseException); </code></td></tr><tr class="even"><td><code>void commit() raises (IDBDatabaseException);</code></td></tr><tr class="odd"><td><code>IDBObjectStoreSync objectStore(in DOMString name) raises (IDBDatabaseException);</code></td></tr></tbody></table>

Attributes
----------

<table><thead><tr class="header"><th>Attribute</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><span id="attr_db"><code>db</code></span></td><td><code>IDBDatabaseSync</code></td><td>The <a href="indexeddb_api#gloss_database_connection">database connection</a> that this transaction is associated with.</td></tr><tr class="even"><td><span id="attr_static"><code>static</code></span></td><td><code>boolean</code></td><td>If true, this transaction is <a href="indexeddb_api#gloss_static">static</a>; if false, this transaction is <a href="indexeddb_api#gloss_dynamic">dynamic</a>.</td></tr></tbody></table>

Methods
-------

### abort()

Call this method to signal a need to cancel the effects of the operations performed by this transaction. When this method is called, the browser ignores all the changes performed to the objects of this database since this transaction was created.

    void abort(
    ) raises (IDBDatabaseException);

##### Exceptions

This method can raise an IDBDatabaseException with the following code:

`NON_TRANSIENT_ERR`  
If this transaction has already been committed or aborted.

### commit()

Call this method to signal that the transaction has completed normally and satisfactorily. When this method is called, the browser durably stores all the changes performed to the objects of the database since this transaction was created.

    void commit(
    ) raises (IDBDatabaseException);

##### Exceptions

This method can raise an IDBDatabaseException with the following codes:

`NON_TRANSIENT_ERR`  
If this transaction has already been committed or aborted.

`RECOVERABLE_ERR`  
If this transaction's scope is dynamic, and the browser cannot commit all of the changes due to another transaction.

### objectStore()

Returns an [object store](indexeddb_api#gloss_object_store) that has already been added to the scope of this transaction.

    IDBObjectStoreSync objectStore(
      in DOMString name
    ) raises (IDBDatabaseException);

##### Parameters

name  
The name of the requested object store.

##### Returns

`IDBObjectStoreSync`  
An object for accessing the requested object store.

##### Exceptions

The method can raise an IDBDatabaseException with the following code:

`NOT_FOUND_ERR`  
If the requested object store is not in this transaction's scope.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBTransactionSync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBTransactionSync</a>
