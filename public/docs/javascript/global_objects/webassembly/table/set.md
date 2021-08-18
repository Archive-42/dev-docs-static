WebAssembly.Table.prototype.set()
=================================

The `set()` prototype method of the [`WebAssembly.Table`](../table) object mutates a reference stored at a given index to a different value.

Syntax
------

    set(index, value)

### Parameters

*index*  
The index of the function reference you want to mutate.

*value*  
The value you want to mutate the reference to. This must be an [exported WebAssembly function](https://developer.mozilla.org/en-US/docs/WebAssembly/Exported_functions), a JavaScript wrapper for an underlying wasm function.

### Return value

Void.

### Exceptions

-   If *index* is greater than or equal to [`Table.prototype.length`](length), a [`RangeError`](../../rangeerror) is thrown.
-   If *value* is not an exported WebAssembly function or `null`, a [`TypeError`](../../typeerror) is thrown.

Examples
--------

### Using Table.set

The following example (see table2.html [source code](https://github.com/mdn/webassembly-examples/blob/master/js-api-examples/table2.html) and [live version](https://mdn.github.io/webassembly-examples/js-api-examples/table2.html)) creates a new WebAssembly Table instance with an initial size of 2 references. We then print out the table length and contents of the two indexes (retrieved via [`Table.prototype.get()`](get)) to show that the length is two, and the indexes currently contain no function references (they currently return [`null`](../../null)).

    var tbl = new WebAssembly.Table({initial:2, element:"anyfunc"});
    console.log(tbl.length);
    console.log(tbl.get(0));
    console.log(tbl.get(1));

We then create an import object that contains a reference to the table:

    var importObj = {
      js: {
        tbl:tbl
      }
    };

Finally, we load and instantiate a wasm module (table2.wasm) using the [`WebAssembly.instantiateStreaming()`](../instantiatestreaming), log the table length, and invoke the two referenced functions that are now stored in the table (the table2.wasm module (see [text representation](https://github.com/mdn/webassembly-examples/blob/master/text-format-examples/table2.was)) adds two function references to the table, both of which print out a simple value):

    WebAssembly.instantiateStreaming(fetch('table2.wasm'), importObject)
    .then(function(obj) {
      console.log(tbl.length);
      console.log(tbl.get(0)());
      console.log(tbl.get(1)());
    });

Note how you've got to include a second function invocation operator at the end of the accessor to actually invoke the referenced function and log the value stored inside it (e.g. `get(0)()` rather than `get(0)`) .

This example shows that we're creating and accessing the table from JavaScript, but the same table is visible and callable inside the wasm instance too.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://webassembly.github.io/spec/js-api/#dom-table-set">WebAssembly JavaScript Interface (WebAssembly JavaScript Interface)<br />
<span class="small">#dom-table-set</span></a></td></tr></tbody></table>

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

`set`

57

16

52

Disabled in the Firefox 52 Extended Support Release (ESR).

No

44

11

57

57

52

Disabled in the Firefox 52 Extended Support Release (ESR).

43

11

7.0

See also
--------

-   [WebAssembly](https://developer.mozilla.org/en-US/docs/WebAssembly) overview page
-   [WebAssembly concepts](https://developer.mozilla.org/en-US/docs/WebAssembly/Concepts)
-   [Using the WebAssembly JavaScript API](https://developer.mozilla.org/en-US/docs/WebAssembly/Using_the_JavaScript_API)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WebAssembly/Table/set" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WebAssembly/Table/set</a>
