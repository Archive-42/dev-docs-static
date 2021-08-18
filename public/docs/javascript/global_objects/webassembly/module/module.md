WebAssembly.Module() constructor
================================

A `WebAssembly.Module()` constructor creates a new Module object containing stateless WebAssembly code that has already been compiled by the browser and can be efficiently [shared with Workers](https://developer.mozilla.org/en-US/docs/Web/API/Worker/postMessage), and instantiated multiple times.

The `WebAssembly.Module()` constructor function can be called to synchronously compile given WebAssembly binary code. However, the primary way to get a `Module` is through an asynchronous compilation function like [`WebAssembly.compile()`](../compile).

Syntax
------

**Warning:** Since compilation for large modules can be expensive, developers should only use the `Module()` constructor when synchronous compilation is absolutely required; the asynchronous [`WebAssembly.compileStreaming()`](../compilestreaming) method should be used at all other times.

    new WebAssembly.Module(bufferSource)

### Parameters

*bufferSource*  
A [typed array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Typed_arrays) or [ArrayBuffer](../../arraybuffer) containing the binary code of the .wasm module you want to compile.

Examples
--------

### Synchronously compiling a WebAssembly module

    var importObject = {
      imports: {
        imported_func: function(arg) {
          console.log(arg);
        }
      }
    };

    function createWasmModule(bytes) {
      return new WebAssembly.Module(bytes);
    }

    fetch('simple.wasm').then(response =>
      response.arrayBuffer()
    ).then(bytes => {
      let mod = createWasmModule(bytes);
      WebAssembly.instantiate(mod, importObject)
      .then(result =>
         result.exports.exported_func()
      );
    })

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://webassembly.github.io/spec/js-api/#dom-module-module">WebAssembly JavaScript Interface (WebAssembly JavaScript Interface)<br />
<span class="small">#dom-module-module</span></a></td></tr></tbody></table>

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

`Module`

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
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WebAssembly/Module/Module" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WebAssembly/Module/Module</a>
