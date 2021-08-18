XRInputSourceArray.forEach()
============================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`XRInputSourceArray`](../xrinputsourcearray) method `forEach()` executes the specified callback once for each input source in the array, starting at index 0 and progressing until the end of the list.

Syntax
------

    xrInputSourceArray.forEach(callback, thisArg);

### Parameters

`callback`  
A function to execute once for each entry in the array `xrInputSourceArray`. The callback accepts up to three parameters:

`currentValue`  
A [`XRInputSource`](../xrinputsource) object which is the value of the item from within the `xrInputSourceArray` which is currently being processed.

 `currentIndex` <span class="badge inline optional">Optional</span>   
An integer value providing the index into the array at which the element given by `currentValue` is located. If you don't need to know the index number, you can omit this.

 `sourceList` <span class="badge inline optional">Optional</span>   
The [`XRInputSourceArray`](../xrinputsourcearray) object which is being processed. If you don't need this information, you may omit this.

 `thisArg` <span class="badge inline optional">Optional</span>   
The value to be used for `this` while executing the callback. Note that if you use [arrow function notation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) (`=>`) to provide the callback, you can omit `thisArg`, since all arrow functions lexically bind `this`.

### Return value

Undefined.

Examples
--------

This example snippet gets the list of inputs for a session and tries to handle each type of input device it supports using.

    let inputSources = xrSession.inputSources;

    inputSources.forEach((input) => {
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
    });

For each input in the llist, the callback dispatches gamepad inputs to a `checkGamepad()` with the input's [`Gamepad`](../gamepad) object, taken from its <span class="page-not-created">`gamepad`</span> property, as an input

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

`forEach`

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

See also
--------

-   [Inputs and input sources](../webxr_device_api/inputs)
-   The `Array` method `forEach()`
-   [`XRInputSource`](../xrinputsource)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourceArray/forEach" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourceArray/forEach</a>
