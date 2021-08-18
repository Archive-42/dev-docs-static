IDBCursorSync
=============

**Draft**

This page is not complete.

**Important**: The synchronous version of the IndexedDB API was originally intended for use only with [Web Workers](web_workers_api/using_web_workers), and was eventually removed from the spec because its need was questionable. It may however be reintroduced in the future if there is enough demand from web developers.

The `IDBCursorSync` interface of the [IndexedDB API](indexeddb_api) represents a [cursor](indexeddb_api#gloss_cursor) for iterating over multiple records in a database. You can have only one instance of `IDBCursorSync` representing a cursor, but you can have an unlimited number of cursors at the same time. Operations are performed on the underlying index or object store. It enables an application to synchronously process all the records in the cursor's range.

Method overview
---------------

<table><tbody><tr class="odd"><td><code>bool continue (in optional any key);</code></td></tr><tr class="even"><td><code>void remove () raises (IDBDatabaseException);</code></td></tr></tbody></table>

Attributes
----------

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Attribute</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><span id="attr_count"><code>count</code></span></td><td><code>readonly unsigned long long</code></td><td>The total number of objects that share the current key.</td></tr><tr class="even"><td><span id="attr_direction"><code>direction</code></span></td><td><code>readonly unsigned short</code></td><td>The <a href="indexeddb_api#gloss_direction">direction</a> of traversal of the cursor. See Constants for possible values.</td></tr><tr class="odd"><td><span id="attr_key"><code>key</code></span></td><td><code>readonly any</code></td><td>The key for the record at the cursor's <a href="indexeddb_api#gloss_position">position</a>.</td></tr><tr class="even"><td><span id="attr_value"><code>value</code></span></td><td><code>any</code></td><td><p>The value for the record at the cursor's position. Setting this attribute can raise an IDBDatabaseException with the following codes:</p><dl><dt><code>DATA_ERR</code></dt><dd>If the underlying object store uses <a href="indexeddb_api#gloss_in-line_key">in-line keys</a> and the property at the <a href="indexeddb_api#gloss_key_path">key path</a> does not match the key in this cursor's position.</dd><dt><code>NOT_ALLOWED_ERR</code></dt><dd>If the underlying index or object store does not support updating the record because it is open in the <code>READ_ONLY</code> or <code>SNAPSHOT_READ</code> mode, or if an index record cannot be changed because the underlying index is <a href="indexeddb_api#gloss_auto-populated">auto-populated</a>.</dd><dt><code>SERIAL_ERR</code></dt><dd>If the data being stored could not be serialized by the internal structured cloning algorithm.</dd></dl></td></tr></tbody></table>

Constants
---------

<table><thead><tr class="header"><th>Constant</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><span id="const_next"><code>NEXT</code></span></td><td>0</td><td>This cursor includes duplicates, and its direction is monotonically increasing in the order of keys.</td></tr><tr class="even"><td><span id="const_next_no_duplicate"><code>NEXT_NO_DUPLICATE</code></span></td><td>1</td><td>This cursor does not include duplicates, and its direction is monotonically increasing in the order of keys.</td></tr><tr class="odd"><td><span id="const_prev"><code>PREV</code></span></td><td>2</td><td>This cursor includes duplicates, and its direction is monotonically decreasing in the order of keys.</td></tr><tr class="even"><td><span id="const_prev_no_duplicate"><code>PREV_NO_DUPLICATE</code></span></td><td>3</td><td>This cursor does not include duplicates, and its direction is monotonically decreasing in the order of keys.</td></tr></tbody></table>

Methods
-------

### continue()

Advances the cursor to the next position along its direction, to the item whose key matches the optional `key` parameter. If no key is specified, advance to the immediate next position. Returns false if the cursor has reached the end of its range; otherwise returns true.

    bool continue (
      in optional any key
    );

##### Parameters

key  
The key to which to move the cursor's position.

### remove()

Deletes the record at the cursor's position, without changing the cursor's position

    void delete (
    ) raises (DatabaseException);

##### Exceptions

This method can raise an IDBDatabaseException with the following code:

`NOT_ALLOWED_ERR`  
If the underlying index or object store does not support updating the record because it is open in the `READ_ONLY` or `SNAPSHOT_READ` mode.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBCursorSync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBCursorSync</a>
