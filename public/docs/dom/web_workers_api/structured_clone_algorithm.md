The structured clone algorithm
==============================

The **structured clone algorithm** copies complex JavaScript objects. It is used internally to transfer data between [Workers](../worker) via [`postMessage()`](../worker/postmessage), storing objects with [IndexedDB](https://developer.mozilla.org/en-US/docs/Glossary/IndexedDB), or copying objects for [other APIs](#see_also). It clones by recursing through the input object while maintaining a map of previously visited references, to avoid infinitely traversing cycles.

Things that don't work with structured clone
--------------------------------------------

-   [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function) objects cannot be duplicated by the structured clone algorithm; attempting to throws a `DATA_CLONE_ERR` exception.
-   Cloning DOM nodes likewise throws a `DATA_CLONE_ERR` exception.
-   Certain object properties are not preserved:
    -   The `lastIndex` property of [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp) objects is not preserved.
    -   Property descriptors, setters, getters, and similar metadata-like features are not duplicated. For example, if an object is marked readonly with a [property descriptor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyDescriptor), it will be read/write in the duplicate, since that's the default.
    -   The prototype chain is not walked or duplicated.

**Note**: Native [`Error`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error) types can be cloned in Chrome, and Firefox is [working on it](https://bugzilla.mozilla.org/show_bug.cgi?id=1556604).

Supported types
---------------

<table><thead><tr class="header"><th>Object type</th><th>Notes</th></tr></thead><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#primitive_values">All primitive types</a></td><td>However, not symbols.</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean">Boolean</a> objects</td><td></td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/String">String</a> objects</td><td></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date">Date</a></td><td></td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp">RegExp</a></td><td><code>lastIndex</code> is not preserved.</td></tr><tr class="even"><td><a href="../blob"><code>Blob</code></a></td><td></td></tr><tr class="odd"><td><a href="../file"><code>File</code></a></td><td></td></tr><tr class="even"><td><a href="../filelist"><code>FileList</code></a></td><td></td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer">ArrayBuffer</a></td><td></td></tr><tr class="even"><td><a href="../arraybufferview">ArrayBufferView</a></td><td>Including other <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Typed_arrays">typed arrays</a>.</td></tr><tr class="odd"><td><a href="../imagebitmap"><code>ImageBitmap</code></a></td><td></td></tr><tr class="even"><td><a href="../imagedata"><code>ImageData</code></a></td><td></td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array">Array</a></td><td></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object">Object</a></td><td><strong>Only</strong> plain objects (e.g. from object literals)</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map">Map</a></td><td></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set">Set</a></td><td></td></tr></tbody></table>

See also
--------

-   [HTML Specification: Safe passing of structured data](https://www.w3.org/TR/html5/infrastructure.html#safe-passing-of-structured-data)
-   [`window.history`](../window/history)
-   [`window.postMessage()`](../window/postmessage)
-   [Web Workers](../web_workers_api)
-   [IndexedDB](../indexeddb_api)
-   [Components.utils.cloneInto](https://developer.mozilla.org/en-US/docs/Components.utils.cloneInto)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Structured_clone_algorithm" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Structured_clone_algorithm</a>
