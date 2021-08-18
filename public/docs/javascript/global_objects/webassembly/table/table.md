WebAssembly.Table() constructor
===============================

The `WebAssembly.Table()` constructor creates a new `Table` object of the given size and element type.

Syntax
------

    new WebAssembly.Table(tableDescriptor)

### Parameters

*tableDescriptor*  
An object that can contain the following members:

*element*  
A string representing the type of value to be stored in the table. At the moment this can only have a value of `"anyfunc"` (functions).

*initial*  
The initial number of elements of the WebAssembly Table.

*maximum <span class="badge inline optional">Optional</span>*  
The maximum number of elements the WebAssembly Table is allowed to grow to.

### Exceptions

-   If `tableDescriptor` is not of type object, a [`TypeError`](../../typeerror) is thrown.
-   If `maximum` is specified and is smaller than `initial`, a [`RangeError`](../../rangeerror) is thrown.

Examples
--------

### Creating a new WebAssembly Table instance

The following example (see table2.html [source code](https://github.com/mdn/webassembly-examples/blob/master/js-api-examples/table2.html) and [live version](https://mdn.github.io/webassembly-examples/js-api-examples/table2.html)) creates a new WebAssembly Table instance with an initial size of 2 elements. We then print out the table length and contents of the two indexes (retrieved via [`Table.prototype.get()`](get) to show that the length is two and both elements are [`null`](../../null).

    var tbl = new WebAssembly.Table({initial:2, element:"anyfunc"});
    console.log(tbl.length);  // "2"
    console.log(tbl.get(0));  // "null"
    console.log(tbl.get(1));  // "null"

We then create an import object that contains the table:

    var importObj = {
      js: {
        tbl:tbl
      }
    };

Finally, we load and instantiate a wasm module (table2.wasm) using the [`WebAssembly.instantiateStreaming()`](../instantiatestreaming) method. The table2.wasm module contains two functions (one that returns 42 and another that returns 83) and stores both into elements 0 and 1 of the imported table (see [text representation](https://github.com/mdn/webassembly-examples/blob/master/js-api-examples/table2.wat)). So after instantiation, the table still has length 2, but the elements now contain callable [Exported WebAssembly Functions](https://developer.mozilla.org/en-US/docs/WebAssembly/Exported_functions) which we can call from JS.

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

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://webassembly.github.io/spec/js-api/#dom-table-table">WebAssembly JavaScript Interface (WebAssembly JavaScript Interface)<br />
<span class="small">#dom-table-table</span></a></td></tr></tbody></table>

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

`Table`

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
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WebAssembly/Table/Table" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WebAssembly/Table/Table</a>
