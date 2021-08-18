WebAssembly.Instance.prototype.exports
======================================

The `exports` readonly property of the [`WebAssembly.Instance`](../instance) object prototype returns an object containing as its members all the functions exported from the WebAssembly module instance, to allow them to be accessed and used by JavaScript.

    instance.exports

Examples
--------

### Using exports

After fetching some WebAssembly bytecode using fetch, we compile and instantiate the module using the [`WebAssembly.instantiateStreaming()`](../instantiatestreaming) function, importing a JavaScript function into the WebAssembly Module in the process. We then call an [Exported WebAssembly function](https://developer.mozilla.org/en-US/docs/WebAssembly/Exported_functions) that is exported by the `Instance`.

    var importObject = {
      imports: {
        imported_func: function(arg) {
          console.log(arg);
        }
      }
    };

    WebAssembly.instantiateStreaming(fetch('simple.wasm'), importObject)
    .then(obj => obj.instance.exports.exported_func());

**Note:** You can also find this example as [instantiate-streaming.html](https://github.com/mdn/webassembly-examples/blob/master/js-api-examples/instantiate-streaming.html) on GitHub ([view it live also](https://mdn.github.io/webassembly-examples/js-api-examples/instantiate-streaming.html)).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://webassembly.github.io/spec/js-api/#dom-instance-exports">WebAssembly JavaScript Interface (WebAssembly JavaScript Interface)<br />
<span class="small">#dom-instance-exports</span></a></td></tr></tbody></table>

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

`exports`

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
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WebAssembly/Instance/exports" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WebAssembly/Instance/exports</a>
