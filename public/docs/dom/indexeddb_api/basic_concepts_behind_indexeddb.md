Basic concepts
==============

**IndexedDB** is a way for you to persistently store data inside a user's browser. Because it lets you create web applications with rich query abilities regardless of network availability, these applications can work both online and offline. IndexedDB is useful for applications that store a large amount of data (for example, a catalog of DVDs in a lending library) and applications that don't need persistent internet connectivity to work (for example, mail clients, to-do lists, and notepads).

About this document
-------------------

This introduction discusses essential concepts and terminology in IndexedDB. It gives you the big picture and explains key concepts.

You'll find the following useful:

-   For an overview of the design and structure of IndexedDB, see [Big Concepts](#concepts).
-   To learn more about IndexedDB terms, see the [Definitions](#definitions) section.
-   For a detailed tutorial on how to use the API, see [Using IndexedDB](using_indexeddb).
-   For the reference documentation on the IndexedDB API, refer back to the main [IndexedDB API](../indexeddb_api) article and its subpages, which document the types of objects used by IndexedDB.
-   For more information on how the browser handles storing your data in the background, read [Browser storage limits and eviction criteria](browser_storage_limits_and_eviction_criteria).

Overview of IndexedDB
---------------------

IndexedDB lets you store and retrieve objects that are indexed with a "key." All changes that you make to the database happen within transactions. Like most web storage solutions, IndexedDB follows a [same-origin policy](https://www.w3.org/Security/wiki/Same_Origin_Policy). So while you can access stored data within a domain, you cannot access data across different domains.

IndexedDB is an [asynchronous](../indexeddb_api#asynchronous_api) API that can be used in most contexts, including [Web Workers](../web_workers_api/using_web_workers). It used to include a [synchronous](../indexeddb_api#synchronous_api) version also, for use in web workers, but this was removed from the spec due to lack of interest by the web community.

IndexedDB used to have a competing spec, WebSQL Database, but the W3C deprecated it on November 18, 2010. While both IndexedDB and WebSQL are solutions for storage, they do not offer the same functionalities. WebSQL Database is a relational database access system, whereas IndexedDB is an indexed table system.

Big concepts
------------

If you have assumptions from working with other types of databases, you might get thrown off when working with IndexedDB. So keep the following important concepts in mind:

-   **IndexedDB databases store key-value pairs.** The values can be complex structured objects, and keys can be properties of those objects. You can create indexes that use any property of the objects for quick searching, as well as sorted enumeration. Keys can be binary objects.

-   **IndexedDB is built on a transactional database model**. Everything you do in IndexedDB always happens in the context of a [transaction](#gloss_transaction). The IndexedDB API provides lots of objects that represent indexes, tables, cursors, and so on, but each of these is tied to a particular transaction. Thus, you cannot execute commands or open cursors outside of a transaction. Transactions have a well-defined lifetime, so attempting to use a transaction after it has completed throws exceptions. Also, transactions auto-commit and cannot be committed manually.

    This transaction model is really useful when you consider what might happen if a user opened two instances of your web app in two different tabs simultaneously. Without transactional operations, the two instances could interfere with each other's modifications. If you are not familiar with transactions in a database, read the [Wikipedia article on transactions](https://en.wikipedia.org/wiki/Database_transaction). Also see [transaction](#gloss_transaction) under the Definitions section.

-   **The IndexedDB API is mostly asynchronous.** The API doesn't give you data by returning values; instead, you have to pass a callback function. You don't "store" a value into the database, or "retrieve" a value out of the database through synchronous means. Instead, you "request" that a database operation happens. You get notified by a DOM event when the operation finishes, and the type of event you get lets you know if the operation succeeded or failed. This sounds a little complicated at first, but there are sanity measures baked in. It's not that different from the way that [XMLHttpRequest](../xmlhttprequest) works.

-   **IndexedDB uses a lot of requests.** Requests are objects that receive the success or failure DOM events that were mentioned previously. They have `onsuccess` and `onerror` properties, and you can call `addEventListener()` and `removeEventListener()` on them. They also have `readyState`, `result`, and `errorCode` properties that tell you the status of the request. The `result` property is particularly magical, as it can be many different things, depending on how the request was generated (for example, an `IDBCursor` instance, or the key for a value that you just inserted into the database).

-   **IndexedDB uses DOM events to notify you when results are available.** DOM events always have a `type` property (in IndexedDB, it is most commonly set to `"success"` or `"error"`). DOM events also have a `target` property that indicates where the event is headed. In most cases, the `target` of an event is the `IDBRequest` object that was generated as a result of doing some database operation. Success events don't bubble up and they can't be canceled. Error events, on the other hand, do bubble, and can be cancelled. This is quite important, as error events abort whatever transactions they're running in, unless they are cancelled.

-   **IndexedDB is object-oriented.** IndexedDB is not a relational database with tables representing collections of rows and columns. This important and fundamental difference affects the way you design and build your applications.

    In a traditional relational data store, you would have a table that stores a collection of rows of data and columns of named types of data. IndexedDB, on the other hand, requires you to create an object store for a type of data and persist JavaScript objects to that store. Each object store can have a collection of indexes that makes it efficient to query and iterate across. If you are not familiar with object-oriented database management systems, read the [Wikipedia article on object database](https://en.wikipedia.org/wiki/Object_database).

-   **IndexedDB does not use Structured Query Language (SQL).** It uses queries on an index that produces a cursor, which you use to iterate across the result set. If you are not familiar with NoSQL systems, read the [Wikipedia article on NoSQL](https://en.wikipedia.org/wiki/NoSQL).

-   <span id="origin">**IndexedDB adheres to a same-origin policy**</span>. An origin is the domain, application layer protocol, and port of a URL of the document where the script is being executed. Each origin has its own associated set of databases. Every database has a name that identifies it within an origin.

    The security boundary imposed on IndexedDB prevents applications from accessing data with a different origin. For example, while an app or a page in [http://www.example.com/app/](https://www.example.com/app/) can retrieve data from [http://www.example.com/dir/](https://www.example.com/dir/), because they have the same origin, it cannot retrieve data from [http://www.example.com:8080/dir/](https://www.example.com:8080/dir/) (different port) or <https://www.example.com/dir/> (different protocol), because they have different origins.

    **Note**: Third party window content (e.g. [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) content) can access the IndexedDB store for the origin it is embedded into, unless the browser is set to [never accept third party cookies](https://support.mozilla.org/en-US/kb/disable-third-party-cookies) (see [bug 1147821](https://bugzilla.mozilla.org/show_bug.cgi?id=1147821).)

Definitions
-----------

This section defines and explains terms used in the IndexedDB API.

### Database

<span id="gloss_database">database</span>  
A repository of information, typically comprising one or more [*object stores*](#gloss_object_store). Each database must have the following:

-   Name. This identifies the database within a specific origin and stays constant throughout its lifetime. The name can be any string value (including an empty string).
-   Current [*version*](#gloss_version). When a database is first created, its version is the integer 1 if not specified otherwise. Each database can have only one version at any given time.

<span id="durable">durable</span>  
In Firefox, IndexedDB used to be **durable**, meaning that in a readwrite transaction [`IDBTransaction.oncomplete`](../idbtransaction/oncomplete) was fired only when all data was guaranteed to have been flushed to disk.

As of Firefox 40, IndexedDB transactions have relaxed durability guarantees to increase performance (see [bug 1112702](https://bugzilla.mozilla.org/show_bug.cgi?id=1112702)), which is the same behavior as other IndexedDB-supporting browsers. In this case the `complete` event is fired after the OS has been told to write the data but potentially before that data has actually been flushed to disk. The event may thus be delivered quicker than before, however, there exists a small chance that the entire transaction will be lost if the OS crashes or there is a loss of system power before the data is flushed to disk. Since such catastrophic events are rare, most consumers should not need to concern themselves further.

**Note**: In Firefox, if you wish to ensure durability for some reason (e.g. you're storing critical data that cannot be recomputed later) you can force a transaction to flush to disk before delivering the `complete` event by creating a transaction using the experimental (non-standard) `readwriteflush` mode (see [`IDBDatabase.transaction`](../idbdatabase/transaction).) This is currently experimental, and can only be used if the `dom.indexedDB.experimental` pref is set to `true` in `about:config`.

<span id="gloss_object_store">object store</span>  
The mechanism by which data is stored in the database. The object store persistently holds records, which are key-value pairs. Records within an object store are sorted according to the *[keys](#gloss_key)* in an ascending order.

Every object store must have a name that is unique within its database. The object store can optionally have a *[key generator](#gloss_keygenerator)* and a *[key path](#gloss_keypath)*. If the object store has a key path, it is using *[in-line keys](#gloss_inline_key)*; otherwise, it is using *[out-of-line keys](#gloss_outofline_key)*.

For the reference documentation on object store, see [`IDBObjectStore`](../idbobjectstore).

<span id="gloss_version">version</span>  
When a database is first created, its version is the integer 1. Each database has one version at a time; a database can't exist in multiple versions at once. The only way to change the version is by opening it with a greater version than the current one. This will start a [`versionchange`](../idbversionchangerequest) *transaction* and fire an [`upgradeneeded`](../idbopendbrequest/upgradeneeded_event) event. The only place where the schema of the database can be updated is inside the handler of that event.

Note: This definition describes the [most recent specification](https://dvcs.w3.org/hg/IndexedDB/raw-file/tip/Overview.html), which is only implemented in up-to-date browsers. Old browsers implemented the now deprecated and removed [`IDBDatabase.setVersion()`](../idbdatabase#setversion()) method.

<span id="gloss_database_connection">database connection</span>  
An operation created by opening a *[database](#gloss_database)*. A given database can have multiple connections at the same time.

<span id="gloss_transaction">transaction</span>  
An atomic set of data-access and data-modification operations on a particular database. It is how you interact with the data in a database. In fact, any reading or changing of data in the database must happen in a transaction.

A database connection can have several active transactions associated with it at a time, so long as the writing transactions do not have overlapping [*scopes*](#scope). The scope of transactions, which is defined at creation, determines which object stores the transaction can interact with and remains constant for the lifetime of the transaction. So, for example, if a database connection already has a writing transaction with a scope that just covers the `flyingMonkey` object store, you can start a second transaction with a scope of the `unicornCentaur` and `unicornPegasus` object stores. As for reading transactions, you can have several of them — even overlapping ones.

Transactions are expected to be short-lived, so the browser can terminate a transaction that takes too long, in order to free up storage resources that the long-running transaction has locked. You can abort the transaction, which rolls back the changes made to the database in the transaction. And you don't even have to wait for the transaction to start or be active to abort it.

The three modes of transactions are: `readwrite`, `readonly`, and `versionchange`. The only way to create and delete object stores and indexes is by using a [`versionchange`](../idbdatabase/versionchange_event) transaction. To learn more about transaction types, see the reference article for [IndexedDB](../indexeddb_api).

Because everything happens within a transaction, it is a very important concept in IndexedDB. To learn more about transactions, especially on how they relate to versioning, see [`IDBTransaction`](../idbtransaction), which also has reference documentation.

<span id="gloss_request">request</span>  
The operation by which reading and writing on a database is done. Every request represents one read or write operation.

<span id="gloss_index">index</span>  
An index is a specialized object store for looking up records in another object store, called the *referenced object store*. The index is a persistent key-value storage where the value part of its records is the key part of a record in the referenced object store. The records in an index are automatically populated whenever records in the referenced object store are inserted, updated, or deleted. Each record in an index can point to only one record in its referenced object store, but several indexes can reference the same object store. When the object store changes, all indexes that refer to the object store are automatically updated.

Alternatively, you can also look up records in an object store using the [key](#gloss_key)*.*

To learn more on using indexes, see [Using IndexedDB](using_indexeddb#using_an_index). For the reference documentation on index, see [IDBKeyRange](../idbkeyrange).

### Key and value

<span id="gloss_key">key</span>  
A data value by which stored values are organized and retrieved in the object store. The object store can derive the key from one of three sources: a *[key generator](#gloss_keygenerator)*, a *[key path](#gloss_keypath)*, or an explicitly specified value. The key must be of a data type that has a number that is greater than the one before it. Each record in an object store must have a key that is unique within the same store, so you cannot have multiple records with the same key in a given object store.

A key can be one of the following types: [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String), [date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date), float, a binary blob, and [array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array). For arrays, the key can range from an empty value to infinity. And you can include an array within an array.

Alternatively, you can also look up records in an object store using the *[index](#gloss_index).*

<span id="gloss_keygenerator">key generator</span>  
A mechanism for producing new keys in an ordered sequence. If an object store does not have a key generator, then the application must provide keys for records being stored. Generators are not shared between stores. This is more a browser implementation detail, because in web development, you don't really create or access key generators.

<span id="gloss_inline_key">in-line key</span>  
A key that is stored as part of the stored value. It is found using a *key path*. An in-line key can be generated using a generator. After the key has been generated, it can then be stored in the value using the key path or it can also be used as a key.

<span id="gloss_outofline_key">out-of-line key</span>  
A key that is stored separately from the value being stored.

<span id="gloss_keypath">key path</span>  
Defines where the browser should extract the key from in the object store or index. A valid key path can include one of the following: an empty string, a JavaScript identifier, or multiple JavaScript identifiers separated by periods or an array containing any of those. It cannot include spaces.

<span id="gloss_value">value</span>  
Each record has a value, which could include anything that can be expressed in JavaScript, including [boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number), [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String), [date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date), [object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object), [array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array), [regexp](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp), [undefined](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined), and null.

When an object or array is stored, the properties and values in that object or array can also be anything that is a valid value.

[Blobs](../blob) and files can be stored, cf. [specification](https://dvcs.w3.org/hg/IndexedDB/raw-file/tip/Overview.html).

### Range and scope

scope  
The set of object stores and indexes to which a transaction applies. The scopes of read-only transactions can overlap and execute at the same time. On the other hand, the scopes of writing transactions cannot overlap. You can still start several transactions with the same scope at the same time, but they just queue up and execute one after another.

cursor  
A mechanism for iterating over multiple records with a *key range*. The cursor has a source that indicates which index or object store it is iterating. It has a position within the range, and moves in a direction that is increasing or decreasing in the order of record keys. For the reference documentation on cursors, see [`IDBCursor`](../idbcursor).

key range  
A continuous interval over some data type used for keys. Records can be retrieved from object stores and indexes using keys or a range of keys. You can limit or filter the range using lower and upper bounds. For example, you can iterate over all values of a key between x and y.

For the reference documentation on key range, see [`IDBKeyRange`](../idbkeyrange).

Limitations
-----------

IndexedDB is designed to cover most cases that need client-side storage. However, it is not designed for a few cases like the following:

-   Internationalized sorting. Not all languages sort strings in the same way, so internationalized sorting is not supported. While the database can't store data in a specific internationalized order, you can sort the data that you've read out of the database yourself. Note, however, that [locale-aware sorting](using_indexeddb#locale-aware_sorting) has been allowed with an experimental flag enabled (currently for Firefox only) since Firefox 43.
-   Synchronizing. The API is not designed to take care of synchronizing with a server-side database. You have to write code that synchronizes a client-side indexedDB database with a server-side database.
-   Full text searching. The API<span style="direction: ltr;"> does not have an</span><span style="direction: ltr;"> equivalent of the `LIKE` operator in SQL. </span>

In addition, be aware that browsers can wipe out the database, such as in the following conditions:

-   The user requests a wipe out. Many browsers have settings that let users wipe all data stored for a given website, including cookies, bookmarks, stored passwords, and IndexedDB data.
-   The browser is in private browsing mode. Some browsers, have "private browsing" (Firefox) or "incognito" (Chrome) modes. At the end of the session, the browser wipes out the database.
-   The disk or quota limit has been reached.
-   The data is corrupt.
-   An incompatible change is made to the feature.

The exact circumstances and browser capabilities change over time, but the general philosophy of the browser vendors is to make the best effort to keep the data when possible.

Next steps
----------

With these big concepts under our belts, we can get to more concrete stuff. For a tutorial on how to use the API, see [Using IndexedDB](using_indexeddb).

See also
--------

-   [<span style="direction: ltr;">Indexed Database API Specification</span>](https://www.w3.org/TR/IndexedDB/)
-   [IndexedDB API Reference](../indexeddb_api)
-   [Using IndexedDB](using_indexeddb)
-   [IndexedDB — The Store in Your Browser](https://msdn.microsoft.com/en-us/scriptjunkie/gg679063.aspx)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API/Basic_Concepts_Behind_IndexedDB" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API/Basic_Concepts_Behind_IndexedDB</a>