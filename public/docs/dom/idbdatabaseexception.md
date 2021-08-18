IDBDatabaseException
====================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Warning**

This interface was removed from the specification and was replaced by usage of [`DOMException`](domexception).

In the [IndexedDB API](indexeddb_api), an `IDBDatabaseException` object represents exception conditions that can be encountered while performing database operations.

Attributes
----------

<table><thead><tr class="header"><th>Attribute</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><span id="attr_code"><code>code</code></span></td><td><code>unsigned short</code></td><td>The most appropriate error code for the condition.</td></tr><tr class="even"><td><span id="attr_message"><code>message</code></span></td><td><code>DOMString</code></td><td>Error message describing the exception raised.</td></tr></tbody></table>

Constants
---------

**Note**

Do not rely on the numeric values of the constants, which might change as the specifications continue to change. Use the constant names instead.

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Constant</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>ABORT_ERR</code></td><td><code>8</code></td><td>A request was aborted, for example, through a call to <a href="idbtransaction#abort"><code>IDBTransaction.abort</code></a>.</td></tr><tr class="even"><td><code>CONSTRAINT_ERR</code></td><td><code>4</code></td><td>A mutation operation in the transaction failed because a constraint was not satisfied. For example, an object, such as an object store or index, already exists and a request attempted to create a new one.</td></tr><tr class="odd"><td><code>DATA_ERR</code></td><td><code>5</code></td><td>Data provided to an operation does not meet requirements.</td></tr><tr class="even"><td><code>NON_TRANSIENT_ERR</code></td><td><code>2</code></td><td>An operation was not allowed on an object. Unless the cause of the error is corrected, retrying the same operation would result in failure.</td></tr><tr class="odd"><td><code>NOT_ALLOWED_ERR</code></td><td><code>6</code></td><td><p>An operation was called on an object where it is not allowed or at a time when it is not allowed. It also occurs if a request is made on a source object that has been deleted or removed.</p><p>More specific variants of this error includes: <code> TRANSACTION_INACTIVE_ERR</code> and <code>READ_ONLY_ERR</code>.</p></td></tr><tr class="even"><td><code>NOT_FOUND_ERR</code></td><td><code>3</code></td><td>The operation failed because the requested database object could not be found; for example, an object store did not exist but was being opened.</td></tr><tr class="odd"><td><code>QUOTA_ERR</code></td><td><code>11</code></td><td>Either there's not enough remaining storage space or the storage quota was reached and the user declined to give more space to the database.</td></tr><tr class="even"><td><code>READ_ONLY_ERR</code></td><td><code>9</code></td><td>A mutation operation was attempted in a <code>READ_ONLY</code> transaction.</td></tr><tr class="odd"><td><code>TIMEOUT_ERR</code></td><td><code>10</code></td><td>A lock for the transaction could not be obtained in a reasonable time.</td></tr><tr class="even"><td><span id="TRANSACTION_INACTIVE_ERR"><code>TRANSACTION_INACTIVE_ERR</code></span></td><td><code>7</code></td><td>A request was made against a transaction that is either not currently active or is already finished.</td></tr><tr class="odd"><td><code>UNKNOWN_ERR</code></td><td><code>1</code></td><td>The operation failed for reasons unrelated to the database itself, and it is not covered by any other error code--for example, a failure due to disk IO errors.</td></tr><tr class="even"><td><code>VER_ERR</code></td><td><code>12</code></td><td>A request to open a database with a version lower than the one it already has. This can only happen with <a href="idbopendbrequest"><code>IDBOpenDBRequest</code></a>.</td></tr></tbody></table>

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

`IDBDatabaseException`

12

≤79

4-14

No

No

No

No

No

4-14

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabaseException" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBDatabaseException</a>
