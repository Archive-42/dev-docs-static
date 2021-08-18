WebAssembly.Table.prototype.get()
=================================

The `get()` prototype method of the [`WebAssembly.Table()`](../table) object retrieves a function reference stored at a given index.

Syntax
------

    get(index)

### Parameters

*index*  
The index of the function reference you want to retrieve.

### Return value

A function reference — this is an [exported WebAssembly function](https://developer.mozilla.org/en-US/docs/WebAssembly/Exported_functions), a JavaScript wrapper for an underlying wasm function.

### Exceptions

If *index* is greater than or equal to [`Table.prototype.length`](length), a [`RangeError`](../../rangeerror) is thrown.

Examples
--------

### Using get

The following example (see [table.html](https://github.com/mdn/webassembly-examples/blob/master/js-api-examples/table.html) on GitHub, and [view it live](https://mdn.github.io/webassembly-examples/js-api-examples/table.html) also) compiles and instantiates the loaded table.wasm byte code using the [`WebAssembly.instantiateStreaming()`](../instantiatestreaming) method. It then retrieves the references stored in the exported table.

    WebAssembly.instantiateStreaming(fetch('table.wasm'))
    .then(function(obj) {
      var tbl = obj.instance.exports.tbl;
      console.log(tbl.get(0)());  // 13
      console.log(tbl.get(1)());  // 42
    });

Note how you've got to include a second function invocation operator at the end of the accessor to actually retrieve the value stored inside the reference (e.g. `get(0)()` rather than `get(0)`) — it is a function rather than a simple value.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://webassembly.github.io/spec/js-api/#dom-table-get">WebAssembly JavaScript Interface (WebAssembly JavaScript Interface)<br />
<span class="small">#dom-table-get</span></a></td></tr></tbody></table>

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

`get`

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
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WebAssembly/Table/get" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WebAssembly/Table/get</a>
