WebAssembly.Memory() constructor
================================

The `WebAssembly.Memory()` constructor creates a new `Memory` object whose [`buffer`](buffer) property is a resizable `ArrayBuffer` or `SharedArrayBuffer` that holds the raw bytes of memory accessed by a WebAssembly `Instance`.

A memory created by JavaScript or in WebAssembly code will be accessible and mutable from both JavaScript and WebAssembly.

Syntax
------

    new WebAssembly.Memory(memoryDescriptor)

### Parameters

*memoryDescriptor*  
An object that can contain the following members:

*initial*  
The initial size of the WebAssembly Memory, in units of WebAssembly pages.

*maximum <span class="badge inline optional">Optional</span>*  
The maximum size the WebAssembly Memory is allowed to grow to, in units of WebAssembly pages. When present, the `maximum` parameter acts as a hint to the engine to reserve memory up front. However, the engine may ignore or clamp this reservation request. Unshared WebAssembly memories don't need to set a `maximum`, but shared memories do.

shared *<span class="badge inline optional">Optional</span>*   
A boolean value that defines whether the memory is a shared memory or not. If set to `true`, it is a shared memory. The default is `false`.

**Note:** A WebAssembly page has a constant size of 65,536 bytes, i.e., 64KiB.

### Exceptions

-   If `memoryDescriptor` is not of type object, a [`TypeError`](../../typeerror) is thrown.
-   If `maximum` is specified and is smaller than `initial`, a [`RangeError`](../../rangeerror) is thrown.

Examples
--------

### Creating a new Memory instance

There are two ways to get a `WebAssembly.Memory` object. The first way is to construct it from JavaScript. The following example creates a new WebAssembly Memory instance with an initial size of 10 pages (640KiB), and a maximum size of 100 pages (6.4MiB). Its `buffer` property will return an `ArrayBuffer`.

    var memory = new WebAssembly.Memory({initial:10, maximum:100});

The second way to get a `WebAssembly.Memory` object is to have it exported by a WebAssembly module. The following example (see [memory.html](https://github.com/mdn/webassembly-examples/blob/master/js-api-examples/memory.html) on GitHub, and [view it live also](https://mdn.github.io/webassembly-examples/js-api-examples/memory.html)) fetches and instantiates the loaded memory.wasm byte code using the [`WebAssembly.instantiateStreaming()`](../instantiatestreaming) method, while importing the memory created in the line above. It then stores some values in that memory, then exports a function and uses it to sum some values.

    WebAssembly.instantiateStreaming(fetch('memory.wasm'), { js: { mem: memory } })
    .then(obj => {
      var i32 = new Uint32Array(memory.buffer);
      for (var i = 0; i < 10; i++) {
        i32[i] = i;
      }
      var sum = obj.instance.exports.accumulate(0, 10);
      console.log(sum);
    });

### Creating a shared memory

By default, WebAssembly memories are unshared. You can create a [shared memory](https://developer.mozilla.org/en-US/docs/WebAssembly/Understanding_the_text_format#shared_memories) by passing `shared: true` in the constructor's initialization object:

    let memory = new WebAssembly.Memory({initial:10, maximum:100, shared:true});

This memory's `buffer` property will return a `SharedArrayBuffer`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://webassembly.github.io/spec/js-api/#dom-memory-memory">WebAssembly JavaScript Interface (WebAssembly JavaScript Interface)<br />
<span class="small">#dom-memory-memory</span></a></td></tr></tbody></table>

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

`Memory`

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

`shared`

74

79

78

No

62

No

No

No

79

No

No

No

See also
--------

-   [WebAssembly](https://developer.mozilla.org/en-US/docs/WebAssembly) overview page
-   [WebAssembly concepts](https://developer.mozilla.org/en-US/docs/WebAssembly/Concepts)
-   [Using the WebAssembly JavaScript API](https://developer.mozilla.org/en-US/docs/WebAssembly/Using_the_JavaScript_API)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WebAssembly/Memory/Memory" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WebAssembly/Memory/Memory</a>
