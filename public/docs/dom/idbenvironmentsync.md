IDBEnvironmentSync
==================

**Draft**

This page is not complete.

**Important**

The synchronous version of the IndexedDB API was originally intended for use only with [Web Workers](web_workers_api/using_web_workers), and was eventually removed from the spec because its need was questionable. It may however be reintroduced in the future if there is enough demand from web developers.

The <span class="notecard inline warning">Unimplemented</span> `IDBEnvironmentSync` interface of the [IndexedDB API](indexeddb_api) will be implemented by [worker](worker) objects.

Attributes
----------

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Attribute</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>indexedDBSync</code></td><td><code>readonly IDBFactorySync</code></td><td>Provides a synchronous means of accessing the capabilities of indexed databases.<div class="notecard note"><strong>Note</strong><p>Until the Indexed Database API specification is finalized, this attribute should be accessed as <code>moz_indexedDBSync</code>.</p></div></td></tr></tbody></table>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBEnvironmentSync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBEnvironmentSync</a>
