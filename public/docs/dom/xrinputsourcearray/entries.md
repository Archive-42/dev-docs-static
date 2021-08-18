XRInputSourceArray.entries()
============================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`XRInputSourceArray`](../xrinputsourcearray) interface's `entries()` method returns a JavaScript `iterator` which can then be used to iterate over the key/value pairs in the input source array. Each item in the array is an [`XRInputSource`](../xrinputsource) object.

Most frequently, you will use this in tandem with statements such as `for...of`.

Syntax
------

    let inputSourceIterator = xrInputSourceArray.entries();

    for (let entry of xrInputSourceArray.entries()) {
      /* ... */
    }

### Parameters

None.

### Return value

An `iterator` which can be used to walk through the list of `XRInputSource` objects included in the input source array.

Examples
--------

This example snippet gets the list of inputs for a session and tries to handle each type of input device it supports using.

    let sources = xrSession.inputSources;

    for (let input of sources.entries()) {
      if (input.gamepad) {
        checkGamepad(input.gamepad);
      } else {
        if (input.targetRayMode === "tracked-pointer" &&
            input.handedness === player.handedness) {
          /* Handle main hand controller */
          handleMainHandInput(input);
        } else {
          /* Handle other inputs */
        }
      }
    }

For each input in the llist, gamepad inputs are dispatched to a `checkGamepad()` with the input's [`Gamepad`](../gamepad) object, taken from its <span class="page-not-created">`gamepad`</span> property, as an input

For other devices, we look for `tracked-pointer` devices in the player's main hand, dispatching those to a `handleMainHandInput()` method.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#xrinputsourcearray">WebXR Device API<br />
<span class="small">The definition of 'XRInputSourceArray' in that specification.</span></a><sup><a href="#spec-iterables">1</a></sup></td><td><span class="spec-wd">Working Draft</span></td><td><code>XRInputSourceArray</code> interface</td></tr></tbody></table>

<span id="spec-iterables">\[1\]</span> See [Iterator-like methods](https://developer.mozilla.org/en-US/docs/MDN/Contribute/Howto/Write_an_API_reference/Information_contained_in_a_WebIDL_file#iterator-like_methods) in [Information contained in a WebIDL file](https://developer.mozilla.org/en-US/docs/MDN/Contribute/Howto/Write_an_API_reference/Information_contained_in_a_WebIDL_file) for information on how an `iterable` declaration in an interface definition causes `entries()`, `forEach()`, `keys()`, and `values()` methods to be exposed from objects that implement the interface.

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

`entries`

79

79

No

No

No

No

No

79

No

No

No

11.2

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourceArray/entries" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourceArray/entries</a>
