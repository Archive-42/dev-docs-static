Worklet.addModule()
===================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `addModule()` method of the [`Worklet`](../worklet) interface loads the module in the given JavaScript file and adds it to the current `Worklet`.

Syntax
------

    addPromise = worklet.addModule(moduleURL);
    addPromise = worklet.addModule(moduleURL, options);

### Parameters

`moduleURL`  
A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) containing the URL of a JavaScript file with the module to add.

 `options` <span class="badge inline optional">Optional</span>   
An object with any of the following options:

-   `credentials`: A <span class="page-not-created">`RequestCredentials`</span> value that indicates whether to send credentials (e.g. cookies and HTTP authentification) when loading the module. Can be one of `"omit"`, `"same-origin"`, or `"include"`. Defaults to `"same-origin"`. See also [`Request.credentials`](../request/credentials).

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves once the module from the given URL has been added. The promise doesn't return any value.

### Exceptions

If `addModule()` fails, it rejects the promise, delivering one of the following errors to the rejection handler.

`AbortError`  
The specified script is invalid or could not be loaded.

`SyntaxError`  
The specified `moduleURL` is invalid.

Examples
--------

### AudioWorklet example

    const audioCtx = new AudioContext();
    const audioWorklet = audioCtx.audioWorklet;
    await audioWorklet.addModule('modules/bypassFilter.js', {
      credentials: 'omit',
    });

### PaintWorklet example

    CSS.paintWorklet.addModule('https://mdn.github.io/houdini-examples/cssPaint/intro/worklets/hilite.js');

Once a [`paintWorklet`](../paintworklet) is included, the CSS [`paint()`](https://developer.mozilla.org/en-US/docs/Web/CSS/paint()) function can be used to include the image created by the worklet:

    @supports (background-image: paint(id)) {
      h1 {
          background-image: paint(hollowHighlights, filled, 3px);
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-worklet-addmodule">HTML Living Standard<br />
<span class="small">The definition of 'addModule()' in that specification.</span></a></td></tr></tbody></table>

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

`addModule`

65

79

76

No

52

No

65

65

79

47

No

9.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Worklet/addModule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Worklet/addModule</a>
