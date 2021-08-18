XRInputSourceArray.values()
===========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`XRInputSourceArray`](../xrinputsourcearray) method `values()` returns a [JavaScript](https://developer.mozilla.org/en-US/docs/Glossary/JavaScript) `iterator` that can walk over the list of [`XRInputSource`](../xrinputsource) objects contained in the array, from first to last.

Syntax
------

    xrInputSourceArray.values();

### Parameters

None.

### Return value

A JavaScript `iterator` that can be used to walk through the list of [`XRInputSource`](../xrinputsource) objects in the array, starting with the first entry (at index 0) and proceeding straight through the list.

Examples
--------

This example snippet walks through each input and calls the function `checkInput()` with each returned value.

    for (const source of xrSession.inputSources.values()) {
      checkInput(source);
    }

Here, `for...of` is used to iterate over the array's contents. Each pass through the loop, `source` is the next [`XRInputSource`](../xrinputsource) in the list. The loop exits once every input has been delivered to `checkInput()`.

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

`values`

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
-   The [`XRInputSourceArray`](../xrinputsourcearray) method [`keys()`](keys)
-   The `Array` method `values()`
-   [`XRInputSource`](../xrinputsource)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourceArray/values" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourceArray/values</a>
