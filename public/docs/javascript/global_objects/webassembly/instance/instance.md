WebAssembly.Instance() constructor
==================================

The `WebAssembly.Instance()` constructor creates a new `Instance` object which is a stateful, executable instance of a [`WebAssembly.Module`](../module).

Syntax
------

**Warning:** Since instantiation for large modules can be expensive, developers should only use the `Instance()` constructor when synchronous instantiation is absolutely required; the asynchronous [`WebAssembly.instantiateStreaming()`](../instantiatestreaming) method should be used at all other times.

    new WebAssembly.Instance(module, importObject)

### Parameters

*module*  
The [`WebAssembly.Module`](../module) object to be instantiated.

 *importObject* <span class="badge inline optional">Optional</span>   
An object containing the values to be imported into the newly-created `Instance`, such as functions or [`WebAssembly.Memory`](../memory) objects. There must be one matching property for each declared import of `module` or else a [`WebAssembly.LinkError`](../linkerror) is thrown.

Examples
--------

### <span class="highlight-span">Synchronously instantiating a WebAssembly module</span>

The `WebAssembly.Instance()` constructor function can be called to synchronously instantiate a given [`WebAssembly.Module`](../module) object, for example:

    const importObject = {
      imports: {
        imported_func: function(arg) {
          console.log(arg);
        }
      }
    };

    fetch('simple.wasm').then(response =>
      response.arrayBuffer()
    ).then(bytes => {
      let mod = new WebAssembly.Module(bytes);
      let instance = new WebAssembly.Instance(mod, importObject);
      instance.exports.exported_func();
    })

However, the preferred way to get an `Instance` is through the asynchronous [`WebAssembly.instantiateStreaming()`](../instantiatestreaming) function, for example like this:

    const importObject = {
      imports: {
        imported_func: function(arg) {
          console.log(arg);
        }
      }
    };

    WebAssembly.instantiateStreaming(fetch('simple.wasm'), importObject)
    .then(obj => obj.instance.exports.exported_func());

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://webassembly.github.io/spec/js-api/#dom-instance-instance">WebAssembly JavaScript Interface (WebAssembly JavaScript Interface)<br />
<span class="small">#dom-instance-instance</span></a></td></tr></tbody></table>

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

`Instance`

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
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WebAssembly/Instance/Instance" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WebAssembly/Instance/Instance</a>
