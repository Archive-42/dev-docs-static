Worklet
=======

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Worklet` interface is a lightweight version of [`Web Workers`](worker) and gives developers access to low-level parts of the rendering pipeline. With Worklets, you can run JavaScript and [WebAssembly](https://developer.mozilla.org/en-US/docs/WebAssembly) code to do graphics rendering or audio processing where high performance is required.

Worklet types
-------------

Worklets are restricted to specific use cases; they cannot be used for arbitrary computations like Web Workers. The `Worklet` interface abstracts properties and methods common to all kind of worklets, and cannot be created directly. Instead, you can use one of the following classes:

<table><colgroup><col style="width: 25%" /><col style="width: 25%" /><col style="width: 25%" /><col style="width: 25%" /></colgroup><thead><tr class="header"><th>Name</th><th>Description</th><th>Location</th><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="paintworklet"><code>PaintWorklet</code></a></td><td><p>For programmatically generating an image where a CSS property expects a file. Access this interface through <a href="css/paintworklet"><code>CSS.paintWorklet</code></a>.</p></td><td><strong>Chrome:</strong> Main thread<br />
<strong>Gecko:</strong> Paint thread</td><td><a href="https://drafts.css-houdini.org/css-paint-api-1/#paint-worklet">CSS Painting API</a></td></tr><tr class="even"><td><a href="audioworklet"><code>AudioWorklet</code></a></td><td>For audio processing with custom AudioNodes.</td><td>Web Audio render thread</td><td><a href="https://webaudio.github.io/web-audio-api/#AudioWorklet">Web Audio API</a></td></tr><tr class="odd"><td><span class="page-not-created"><code>AnimationWorklet</code></span></td><td>For creating scroll-linked and other high performance procedural animations.</td><td>Compositor thread</td><td><a href="https://wicg.github.io/animation-worklet/">CSS Animation Worklet API</a></td></tr><tr class="even"><td><span class="page-not-created"><code>LayoutWorklet</code></span></td><td>For defining the positioning and dimensions of custom elements.</td><td></td><td><a href="https://drafts.css-houdini.org/css-layout-api-1/#layout-worklet">CSS Layout API</a></td></tr></tbody></table>

For 3D rendering with [WebGL](webgl_api), you don't use Worklets. Instead, you write Vertex Shaders and Fragment Shaders using GLSL code, and those shaders will then run on the graphics card.

Properties
----------

*The Worklet interface does not define any properties.*

Methods
-------

 [`Worklet.addModule()`](worklet/addmodule) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Adds the script module at the given URL to the current worklet.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#worklets-worklet">HTML Living Standard<br />
<span class="small">The definition of 'Worklet' in that specification.</span></a></td></tr></tbody></table>

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

`Worklet`

65

79

76

No

52

14.1

65

65

79

47

14.5

9.0

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

See also
--------

-   [Houdini: Demystifying CSS](https://developers.google.com/web/updates/2016/05/houdini) on Google Developers (May 2016)
-   [AudioWorklet :: What, Why, and How](https://www.youtube.com/watch?v=g1L4O1smMC0&t=1m33s) on YouTube (November 2017)
-   [Enter AudioWorklet](https://developers.google.com/web/updates/2017/12/audio-worklet) on Google Developers (December 2017)
-   [Animation Worklet - HTTP203 Advent](https://www.youtube.com/watch?v=ZPkMMShYxKU&t=0m19s) on YouTube (December 2017)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Worklet" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Worklet</a>
