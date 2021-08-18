# IDBFactorySync

**Draft**

This page is not complete.

**Important**: The synchronous version of the IndexedDB API was originally intended for use only with [Web Workers](web_workers_api/using_web_workers), and was eventually removed from the spec because its need was questionable. It may however be reintroduced in the future if there is enough demand from web developers.

The `IDBFactorySync` interface of the [IndexedDB API](indexeddb_api) provide a synchronous means of accessing the capabilities of indexed databases.

## Method overview

<table><tbody><tr class="odd"><td><code>IDBDatabaseSync open (in DOMString name, in DOMString description, in optional boolean modifyDatabase) raises (IDBDatabaseException);</code></td></tr></tbody></table>

## Methods

### open()

Opens and returns a [connection to a database](indexeddb_api#gloss_database_connection). Blocks the calling thread until the connection object is ready to return. If there is already a database with the specified name, it uses that one; otherwise, it creates the database using the specified name and description.

    IDBDatabaseSync open (
      in DOMString name,
      in DOMString description
    ) raises (IDBDatabaseException);

##### Parameters

name  
The name for the database.

description  
The description for the database.

##### Returns

`IDBDatabaseSync`  
An object to access the open database.

##### Exceptions

This method can raise an IDBDatabaseException with the following codes:

`NON_TRANSIENT_ERR`  
If the `name` parameter is not valid. A valid name is any string including the empty string.

`UNKNOWN_ERR`  
If an error occurs while the database is being opened.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBFactorySync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBFactorySync</a>
