XRInputSourceArray.length
=========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The read-only `length` property returns an integer value indicating the number of items in the input source list represented by the [`XRInputSourceArray`](../xrinputsourcearray) object.

Syntax
------

    let inputSourceCount = xrInputSourceArray.length;

### Value

An integer value indicating the number of [`XRInputSource`](../xrinputsource) objects representing WebXR input sources are includled in the array.

Examples
--------

In this example, a game that requires at least one input source uses `length` to check this before proceeding to allow the user to play the game.

    let sources = xrSession.inputSources;

    if (sources.length === 0) {
      showAlertDialog("You need to have at least one controller to play Super Duper Shark Jump Fest 9000.",
                      [
                        { label: "Shop Now", url: "https://www.amazon.com/s?k=vr+controllers" },
                        { label: "Quit" handler: quitGame }
                      ]);
    }

Here, if `length` is 0, a hypothetical `showAlertDialog()` function is called with a prompt string explaining the need for a controller, and an array of objects, each describing a button and what should happen when it's clicked. The first takes the user to an Amazon.com search for VR controllers, and the second calls a `quitGame()` function to start shutting the game program down.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrinputsourcearray-length">WebXR Device API<br />
<span class="small">The definition of 'XRInputSourceArray.length' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourceArray/length" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourceArray/length</a>
