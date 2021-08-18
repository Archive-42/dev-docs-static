XRInputSourceArray.keys()
=========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `keys()` method in the [`XRInputSourceArray`](../xrinputsourcearray) interface returns a [JavaScript](https://developer.mozilla.org/en-US/docs/Glossary/JavaScript) `iterator` which can then be used to iterate over the keys used to reference each item in the array of input sources.

Syntax
------

    xrInputSourceArray.keys();

### Parameters

None.

### Return value

A JavaScript `iterator` that can be used to walk through the keys for each entry in the list of input sources. The values returned by the iterator are the indexes of each entry in the list; that is, the numbers 0, 1, 2, and so forth through the index of the last item in the list.

Examples
--------

This example snippet gets the list of inputs for a session and tries to handle each type of input device it supports using.

    for (const inputIdx of xrSession.inputSources.keys()) {
      /* the keys are the indexes into the list of inputs */
      checkInput(xrSession.inputSources[inputIdx]);
    }

Here, `for...of` is used to iterate over each of the keys. For each key, the input is retrieved using the index with array notation: `xrSession.inputSources[inputIdx]`.

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

`keys`

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
-   The [`XRInputSourceArray`](../xrinputsourcearray) method [`values()`](values)
-   The `Array` method `keys()`
-   [`XRInputSource`](../xrinputsource)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourceArray/keys" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourceArray/keys</a>
