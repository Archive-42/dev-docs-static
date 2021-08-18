XRInputSourceArray
==================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The interface `XRInputSourceArray` represents a *live* list of WebXR input sources, and is used as the return value of the [`XRSession`](xrsession) property [`inputSources`](xrsession/inputsources). Each entry is an [`XRInputSource`](xrinputsource) representing one input device connected to the WebXR system.

In addition to being able to access the input sources in the list using standard array notation (that is, with index numbers insize square brackets), methods are available to allow the use of iterators and the [`forEach()`](xrinputsourcearray/foreach) method is also available.

Properties
----------

*The following properties are available on `XRInputSourceArray` objects.*

 [`length`](xrinputsourcearray/length) <span class="badge inline readonly">Read only </span>   
The number of [`XRInputSource`](xrinputsource) objects in the list.

Methods
-------

*The following methods are available on `XRInputSourceArray` objects. You may also use the features of the `Symbol` type.*

[`entries()`](xrinputsourcearray/entries)  
Returns an `iterator` you can use to walk the list of key/value pairs in the list. Each item returned is an array whose first value is the index and whose second value is the [`XRInputSource`](xrinputsource) at that index.

[`forEach()`](xrinputsourcearray/foreach)  
Iterates over each item in the list, in order from first to last.

[`keys()`](xrinputsourcearray/keys)  
A list of the keys corresponding to the entries in the input source list.

[`values()`](xrinputsourcearray/values)  
Returns an `iterator` you can use to go through all the values in the list. Each item is a single [`XRInputSource`](xrinputsource) object.

In addition to these methods, you may use array notation to access items in the list by index For example, the snippet of code below calls a function `handleInput()`, passing into it the first item in the input source list, if the list isn't empty.

    let sources = xrSession.inputSources;
    if (sources.length > 0) {
      handleInput(sources[0]);
    }

Examples
--------

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#xrinputsourcearray-interface">WebXR Device API<br />
<span class="small">The definition of 'XRInputSourceArray' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XRInputSourceArray`

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

`length`

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

`@@iterator`

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

12.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourceArray" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourceArray</a>
