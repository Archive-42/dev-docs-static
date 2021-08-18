WebAssembly.Table.prototype.grow()
==================================

The `grow()` prototype method of the [`WebAssembly.Table`](../table) object increases the size of the Table instance by a specified number of elements.

Syntax
------

    grow(number)

### Parameters

*number*  
The number of elements you want to grow the table by.

### Return value

The previous length of the table.

### Exceptions

If the `grow()` operation fails for whatever reason, a [`RangeError`](../../rangeerror) is thrown.

Examples
--------

### Using grow

The following example creates a new WebAssembly Table instance with an initial size of 2 and a maximum size of 10.

    var table = new WebAssembly.Table({ element: "anyfunc", initial: 2, maximum: 10 });

You can then grow the table by 1 with the following:

    console.log(table.length);   // "2"
    console.log(table.grow(1));  // "2"
    console.log(table.length);   // "3"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://webassembly.github.io/spec/js-api/#dom-table-grow">WebAssembly JavaScript Interface (WebAssembly JavaScript Interface)<br />
<span class="small">#dom-table-grow</span></a></td></tr></tbody></table>

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

`grow`

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
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WebAssembly/Table/grow" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WebAssembly/Table/grow</a>
