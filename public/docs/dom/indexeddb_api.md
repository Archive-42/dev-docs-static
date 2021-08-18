# IndexedDB API

IndexedDB is a low-level API for client-side storage of significant amounts of structured data, including files/blobs. This API uses indexes to enable high-performance searches of this data. While [Web Storage](web_storage_api) is useful for storing smaller amounts of data, it is less useful for storing larger amounts of structured data. IndexedDB provides a solution. This is the main landing page for MDN's IndexedDB coverage — here we provide links to the full API reference and usage guides, browser support details, and some explanation of key concepts.

**Note:** This feature is available in [Web Workers](web_workers_api).

**Note**: IndexedDB API is powerful, but may seem too complicated for simple cases. If you'd prefer a simple API, try libraries in [See also](#see_also) section that make IndexedDB more programmer-friendly.

## Key concepts and usage

IndexedDB is a transactional database system, like an SQL-based RDBMS. However, unlike SQL-based RDBMSes, which use fixed-column tables, IndexedDB is a JavaScript-based object-oriented database. IndexedDB lets you store and retrieve objects that are indexed with a **key**; any objects supported by the [structured clone algorithm](web_workers_api/structured_clone_algorithm) can be stored. You need to specify the database schema, open a connection to your database, and then retrieve and update data within a series of **transactions**.

- Read more about the [Concepts behind IndexedDB](indexeddb_api/basic_concepts_behind_indexeddb).
- Learn to use IndexedDB asynchronously from first principles with our [Using IndexedDB](indexeddb_api/using_indexeddb) guide.
- Combine IndexedDB for storing data offline with Service Workers for storing assets offline, as outlined in [Making PWAs work offline with Service workers](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Offline_Service_workers).

**Note**: Like most web storage solutions, IndexedDB follows a [same-origin policy](https://www.w3.org/Security/wiki/Same_Origin_Policy). So while you can access stored data within a domain, you cannot access data across different domains.

### Synchronous and asynchronous

Operations performed using IndexedDB are done asynchronously, so as not to block applications. IndexedDB originally included both synchronous and asynchronous APIs. The synchronous API was intended for use only with [Web Workers](web_workers_api/using_web_workers) but was removed from the spec because it was unclear whether it was needed. However, the synchronous API may be reintroduced if there is enough demand from web developers.

### Storage limits and eviction criteria

There are a number of web technologies that store data of one kind or another on the client side (i.e. on your local disk). IndexedDB is most commonly talked about. The process by which the browser works out how much space to allocate to web data storage and what to delete when that limit is reached is not simple, and differs between browsers. [Browser storage limits and eviction criteria](indexeddb_api/browser_storage_limits_and_eviction_criteria) attempts to explain how this works, at least in the case of Firefox.

## Interfaces

To get access to a database, call [`open()`](idbfactory/open) on the [`indexedDB`](windoworworkerglobalscope/indexeddb) attribute of a [window](window) object. This method returns an [`IDBRequest`](idbrequest) object; asynchronous operations communicate to the calling application by firing events on [`IDBRequest`](idbrequest) objects.

### Connecting to a database

[`IDBEnvironment`](idbenvironment)  
Provides access to IndexedDB functionality. It is implemented by the [`window`](window) and [`worker`](worker) objects. This interface isn't part of the 2.0 specification.

[`IDBFactory`](idbfactory)  
Provides access to a database. This is the interface implemented by the global object [`indexedDB`](windoworworkerglobalscope/indexeddb) and is therefore the entry point for the API.

[`IDBOpenDBRequest`](idbopendbrequest)  
Represents a request to open a database.

[`IDBDatabase`](idbdatabase)  
Represents a connection to a database. It's the only way to get a transaction on the database.

### Retrieving and modifying data

[`IDBTransaction`](idbtransaction)  
Represents a transaction. You create a transaction on a database, specify the scope (such as which object stores you want to access), and determine the kind of access (read only or readwrite) that you want.

[`IDBRequest`](idbrequest)  
Generic interface that handles database requests and provides access to results.

[`IDBObjectStore`](idbobjectstore)  
Represents an object store that allows access to a set of data in an IndexedDB database, looked up via primary key.

[`IDBIndex`](idbindex)  
Also allows access to a subset of data in an IndexedDB database, but uses an index to retrieve the record(s) rather than the primary key. This is sometimes faster than using [`IDBObjectStore`](idbobjectstore).

[`IDBCursor`](idbcursor)  
Iterates over object stores and indexes.

[`IDBCursorWithValue`](idbcursorwithvalue)  
Iterates over object stores and indexes and returns the cursor's current value.

[`IDBKeyRange`](idbkeyrange)  
Defines a key range that can be used to retrieve data from a database in a certain range.

[`IDBLocaleAwareKeyRange`](idblocaleawarekeyrange) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Defines a key range that can be used to retrieve data from a database in a certain range, sorted according to the rules of the locale specified for a certain index (see [`createIndex()`'s optionalParameters](idbobjectstore/createindex#parameters).). This interface isn't part of the 2.0 specification.

### Custom event interfaces

This specification fires events with the following custom interface:

[`IDBVersionChangeEvent`](idbversionchangeevent)  
The `IDBVersionChangeEvent` interface indicates that the version of the database has changed, as the result of an [`IDBOpenDBRequest.onupgradeneeded`](idbopendbrequest/onupgradeneeded) event handler function.

### Obsolete interfaces

An early version of the specification also defined the following, now removed, interfaces. They are still documented in case you need to update previously written code:

<span class="page-not-created">`IDBVersionChangeRequest`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Represents a request to change the version of a database. The way to change the version of the database has since changed (by calling [`IDBFactory.open`](idbfactory/open) without also calling <span class="page-not-created">`IDBDatabase.setVersion`</span>), and the interface [`IDBOpenDBRequest`](idbopendbrequest) now has the functionality of the removed <span class="page-not-created">`IDBVersionChangeRequest`</span>.

[`IDBDatabaseException`](idbdatabaseexception) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Represents exception conditions that can be encountered while performing database operations.

[`IDBTransactionSync`](idbtransactionsync) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Sync version of [`IDBTransaction`](idbtransaction).

[`IDBObjectStoreSync`](idbobjectstoresync) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Sync version of [`IDBObjectStore`](idbobjectstore).

[`IDBIndexSync`](idbindexsync) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Sync version of [`IDBIndex`](idbindex).

[`IDBFactorySync`](idbfactorysync) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Sync version of [`IDBFactory`](idbfactory).

[`IDBEnvironmentSync`](idbenvironmentsync) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Sync version of [`IDBEnvironment`](idbenvironment).

[`IDBDatabaseSync`](idbdatabasesync) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Sync version of [`IDBDatabase`](idbdatabase).

[`IDBCursorSync`](idbcursorsync) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Sync version of [`IDBCursor`](idbcursor).

## Examples

- [eLibri:](https://marco-c.github.io/eLibri/) A powerful library and eBook reader application, written by Marco Castelluccio, winner of the IndexedDB Mozilla DevDerby.
- [To-do Notifications](https://github.com/chrisdavidmills/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/)): The reference application for the examples in the reference docs.
- [Storing images and files in IndexedDB](https://hacks.mozilla.org/2012/02/storing-images-and-files-in-indexeddb/)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/">Indexed Database API 2.0</a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/IndexedDB/">Indexed Database API 2.0</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

## See also

- [localForage](https://localforage.github.io/localForage/): A Polyfill providing a simple name:value syntax for client-side data storage, which uses IndexedDB in the background, but falls back to WebSQL and then localStorage in browsers that don't support IndexedDB.
- [Dexie.js](https://dexie.org/): A wrapper for IndexedDB that allows much faster code development via nice, simple syntax.
- [ZangoDB](https://github.com/erikolson186/zangodb): A MongoDB-like interface for IndexedDB that supports most of the familiar filtering, projection, sorting, updating and aggregation features of MongoDB.
- [JsStore](https://jsstore.net/): An IndexedDB wrapper with SQL like syntax.
- [MiniMongo](https://github.com/mWater/minimongo): A client-side in-memory mongodb backed by localstorage with server sync over http. MiniMongo is used by MeteorJS.
- [PouchDB](https://pouchdb.com): A client-side implementation of CouchDB in the browser using IndexedDB
- [idb](https://www.npmjs.com/package/idb): A tiny (~1.15k) library that mostly mirrors the IndexedDB API, but with small improvements that make a big difference to usability.
- [idb-keyval](https://www.npmjs.com/package/idb-keyval): A super-simple-small (~600B) promise-based keyval store implemented with IndexedDB
- [sifrr-storage:](https://www.npmjs.com/package/@sifrr/storage) A small (~2kB) promise based library for client side key-value storage. Works with IndexedDB, localStorage, WebSQL, Cookies. Can automatically use supported storage available based on priority.
- [lovefield](https://github.com/google/lovefield): <span class="mr-2 text-gray-dark">Lovefield is a relational database for web apps. Written in JavaScript, works cross-browser. Provides SQL-like APIs that are fast, safe, and easy to use.</span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API</a>
