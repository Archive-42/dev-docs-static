&lt;canvas&gt;: The Graphics Canvas element
===========================================

Use the `<canvas>` with either the [canvas scripting API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API) or the [WebGL API](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API) to draw graphics and animations.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#embedded_content">embedded content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td>Transparent but with no <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#interactive_content">interactive content</a> descendants except for <a href="a"><code>&lt;a&gt;</code></a> elements, <a href="button"><code>&lt;button&gt;</code></a> elements, <a href="input"><code>&lt;input&gt;</code></a> elements whose <a href="input#attr-type"><code>type</code></a> attribute is <code>checkbox</code>, <code>radio</code>, or <code>button</code>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement"><code>HTMLCanvasElement</code></a></td></tr></tbody></table>

Attributes
----------

This element's attributes include the [global attributes](../global_attributes).

`height`  
The height of the coordinate space in CSS pixels. Defaults to 150.

 `moz-opaque` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Lets the canvas know whether or not translucency will be a factor. If the canvas knows there's no translucency, painting performance can be optimized. This is only supported by Mozilla-based browsers; use the standardized [`canvas.getContext('2d', { alpha: false })`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/getContext) instead.

`width`  
The width of the coordinate space in CSS pixels. Defaults to 300.

Usage notes
-----------

### Alternative content

You may (and should) provide alternate content inside the `<canvas>` block. That content will be rendered both on older browsers that don't support canvas and in browsers with JavaScript disabled. Providing a useful fallback text or sub DOM helps to [make the canvas more accessible](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Hit_regions_and_accessibility).

### Required &lt;/canvas&gt; tag

Unlike the [`<img>`](img) element, the [`<canvas>`](canvas) element **requires** the closing tag (`</canvas>`).

### Sizing the canvas using CSS versus HTML

The displayed size of the canvas can be changed using CSS, but if you do this the image is scaled during rendering to fit the styled size, which can make the final graphics rendering end up being distorted.

It is better to specify your canvas dimensions by setting the `width` and `height` attributes directly on the `<canvas>` elements, either directly in the HTML or by using JavaScript.

### Maximum canvas size

The maximum size of a `<canvas>` element is very large, but the exact size depends on the browser. The following is some data we've collected from various tests and other sources (e.g. [Stack Overflow](https://stackoverflow.com/questions/6081483/maximum-size-of-a-canvas-element)):

<table><thead><tr class="header"><th>Browser</th><th>Maximum height</th><th>Maximum width</th><th>Maximum area</th></tr></thead><tbody><tr class="odd"><td>Chrome</td><td>32,767 pixels</td><td>32,767 pixels</td><td>268,435,456 pixels (i.e., 16,384 x 16,384)</td></tr><tr class="even"><td>Firefox</td><td>32,767 pixels</td><td>32,767 pixels</td><td>472,907,776 pixels (i.e., 22,528 x 20,992)</td></tr><tr class="odd"><td>Safari</td><td>32,767 pixels</td><td>32,767 pixels</td><td>268,435,456 pixels (i.e., 16,384 x 16,384)</td></tr><tr class="even"><td>IE</td><td>8,192 pixels</td><td>8,192 pixels</td><td>?</td></tr></tbody></table>

**Note**: Exceeding the maximum dimensions or area renders the canvas unusable — drawing commands will not work.

Examples
--------

### HTML

This code snippet adds a canvas element to your HTML document. A fallback text is provided if a browser is unable to render the canvas, or if can't read a canvas.

    <canvas width="300" height="300">
      An alternative text describing what your canvas displays.
    </canvas>

### JavaScript

Then in the JavaScript code, call [`HTMLCanvasElement.getContext()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/getContext) to get a drawing context and start drawing onto the canvas:

    const canvas = document.querySelector('canvas');
    const ctx = canvas.getContext('2d');
    ctx.fillStyle = 'green';
    ctx.fillRect(10, 10, 100, 100);

### Result

Accessibility concerns
----------------------

### Alternative content

The `<canvas>` element on its own is just a bitmap and does not provide information about any drawn objects. Canvas content is not exposed to accessibility tools as semantic HTML is. In general, you should avoid using canvas in an accessible website or app. The following guides can help to make it more accessible.

-   [MDN Hit regions and accessibility](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Hit_regions_and_accessibility)
-   [Canvas accessibility use cases](https://www.w3.org/WAI/PF/HTML/wiki/Canvas_Accessibility_Use_Cases)
-   [Canvas element accessibility issues](https://www.w3.org/html/wg/wiki/AddedElementCanvas)
-   [HTML5 Canvas Accessibility in Firefox 13 – by Steve Faulkner](https://developer.paciellogroup.com/blog/2012/06/html5-canvas-accessibility-in-firefox-13/)
-   [Best practices for interactive canvas elements](https://html.spec.whatwg.org/multipage/scripting.html#best-practices)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#the-canvas-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;canvas&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/semantics-scripting.html#the-canvas-element">HTML5<br />
<span class="small">The definition of '&lt;canvas&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`canvas`

1

12

1.5

\["Before Firefox 5, the canvas width and height were signed integers instead of unsigned integers.", "Prior to Firefox 6, a &lt;canvas&gt; element with a zero width or height would be rendered as if it had default dimensions.", "Before Firefox 12, if JavaScript is disabled, the &lt;canvas&gt; element was being rendered instead of showing the fallback content as per the specification. Since then, the fallback content is rendered instead."\]

9

9

2

Although early versions of Apple's Safari browser don't require the closing tag, the specification indicates that it is required, so you should be sure to include it for broadest compatibility. Versions of Safari prior to version 2 will render the content of the fallback in addition to the canvas itself unless you use CSS tricks to mask it.

37

18

4

\["Before Firefox 5, the canvas width and height were signed integers instead of unsigned integers.", "Prior to Firefox 6, a &lt;canvas&gt; element with a zero width or height would be rendered as if it had default dimensions.", "Before Firefox 12, if JavaScript is disabled, the &lt;canvas&gt; element was being rendered instead of showing the fallback content as per the specification. Since then, the fallback content is rendered instead."\]

10.1

1

1.0

`height`

1

12

1.5

\["Before Firefox 5, the canvas width and height were signed integers instead of unsigned integers.", "Prior to Firefox 6, a &lt;canvas&gt; element with a zero width or height would be rendered as if it had default dimensions.", "Before Firefox 12, if JavaScript is disabled, the &lt;canvas&gt; element was being rendered instead of showing the fallback content as per the specification. Since then, the fallback content is rendered instead."\]

9

9

2

Although early versions of Apple's Safari browser don't require the closing tag, the specification indicates that it is required, so you should be sure to include it for broadest compatibility. Versions of Safari prior to version 2 will render the content of the fallback in addition to the canvas itself unless you use CSS tricks to mask it.

37

18

4

\["Before Firefox 5, the canvas width and height were signed integers instead of unsigned integers.", "Prior to Firefox 6, a &lt;canvas&gt; element with a zero width or height would be rendered as if it had default dimensions.", "Before Firefox 12, if JavaScript is disabled, the &lt;canvas&gt; element was being rendered instead of showing the fallback content as per the specification. Since then, the fallback content is rendered instead."\]

10.1

1

1.0

`moz-opaque`

No

No

3.5

No

No

No

No

No

4

No

No

No

`width`

1

12

1.5

\["Before Firefox 5, the canvas width and height were signed integers instead of unsigned integers.", "Prior to Firefox 6, a &lt;canvas&gt; element with a zero width or height would be rendered as if it had default dimensions.", "Before Firefox 12, if JavaScript is disabled, the &lt;canvas&gt; element was being rendered instead of showing the fallback content as per the specification. Since then, the fallback content is rendered instead."\]

9

9

2

Although early versions of Apple's Safari browser don't require the closing tag, the specification indicates that it is required, so you should be sure to include it for broadest compatibility. Versions of Safari prior to version 2 will render the content of the fallback in addition to the canvas itself unless you use CSS tricks to mask it.

37

18

4

\["Before Firefox 5, the canvas width and height were signed integers instead of unsigned integers.", "Prior to Firefox 6, a &lt;canvas&gt; element with a zero width or height would be rendered as if it had default dimensions.", "Before Firefox 12, if JavaScript is disabled, the &lt;canvas&gt; element was being rendered instead of showing the fallback content as per the specification. Since then, the fallback content is rendered instead."\]

10.1

1

1.0

See also
--------

-   [MDN canvas portal](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
-   [Canvas tutorial](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial)
-   [Canvas cheat sheet](https://simon.html5.org/dump/html5-canvas-cheat-sheet.html)
-   [Canvas-related demos](https://developer.mozilla.org/en-US/docs/Web/Demos_of_open_web_technologies)
-   [Canvas introduction by Apple](https://developer.apple.com/library/archive/documentation/AudioVideo/Conceptual/HTML-canvas-guide/Introduction/Introduction.html)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas</a>
