VisualViewport
==============

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `VisualViewport` interface of the [Visual Viewport API](visual_viewport_api) represents the visual viewport for a given window. For a page containing iframes, each iframe, as well as the containing page, will have a unique window object. Each window on a page will have a unique `VisualViewport` representing the properties associated with that window.

You can get a window's visual viewport using [`Window.visualViewport`](window/visualviewport).

**Note**: Only the top-level window has a visual viewport that's distinct from the layout viewport. Therefore, it's generally only the `VisualViewport` object of the top-level window that's useful. For an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe), visual viewport metrics like [`VisualViewport.width`](visualviewport/width) always correspond to layout viewport metrics like [`document.documentElement.clientWidth`](element/clientwidth).

Properties
----------

*`VisualViewport` also inherits properties from its parent, [`EventTarget`](eventtarget).*

 [`VisualViewport.offsetLeft`](visualviewport/offsetleft) <span class="badge inline readonly">Read only </span>   
Returns the offset of the left edge of the visual viewport from the left edge of the layout viewport in CSS pixels.

 [`VisualViewport.offsetTop`](visualviewport/offsettop) <span class="badge inline readonly">Read only </span>   
Returns the offset of the top edge of the visual viewport from the top edge of the layout viewport in CSS pixels.

 [`VisualViewport.pageLeft`](visualviewport/pageleft) <span class="badge inline readonly">Read only </span>   
Returns the x coordinate of the visual viewport relative to the initial containing block origin of the top edge in CSS pixels.

 [`VisualViewport.pageTop`](visualviewport/pagetop) <span class="badge inline readonly">Read only </span>   
Returns the y coordinate of the visual viewport relative to the initial containing block origin of the top edge in CSS pixels.

 [`VisualViewport.width`](visualviewport/width) <span class="badge inline readonly">Read only </span>   
Returns the width of the visual viewport in CSS pixels.

 [`VisualViewport.height`](visualviewport/height) <span class="badge inline readonly">Read only </span>   
Returns the height of the visual viewport in CSS pixels.

 [`VisualViewport.scale`](visualviewport/scale) <span class="badge inline readonly">Read only </span>   
Returns the pinch-zoom scaling factor applied to the visual viewport.

Events
------

Listen to these events using `addEventListener()` or by assigning an event listener to the relevant `oneventname` property of this interface.

`resize`  
Fired when the visual viewport is resized.  
Also available via the [`VisualViewport.onresize`](visualviewport/onresize) property.

`scroll`  
Fired when the visual viewport is scrolled.  
Also available via the [`VisualViewport.onscroll`](visualviewport/onscroll) property.

Examples
--------

### Hiding an overlaid box on zoom

This example, taken from the [Visual Viewport README](https://github.com/WICG/visual-viewport), shows how to write a simple bit of code that will hide an overlaid box (which might contain an advert, say) when the user zooms in. This is a nice way to improve the user experience when zooming in on pages. A [live sample](https://wicg.github.io/visual-viewport/examples/hide-on-zoom.html) is also available.

    var bottomBar = document.getElementById('bottombar');
    var viewport = window.visualViewport;

    function resizeHandler() {
       if (viewport.scale > 1.3)
         bottomBar.style.display = "none";
       else
         bottomBar.style.display = "block";
    }

    window.visualViewport.addEventListener('resize', resizeHandler);

### Simulating position: device-fixed

This example, also taken from the [Visual Viewport README](https://github.com/WICG/visual-viewport), shows how to use this API to simulate `position: device-fixed`, which fixes elements to the visual viewport. A [live sample](https://wicg.github.io/visual-viewport/examples/fixed-to-viewport.html) is also available.

    var bottomBar = document.getElementById('bottombar');
    var viewport = window.visualViewport;
    function viewportHandler() {
      var layoutViewport = document.getElementById('layoutViewport');

      // Since the bar is position: fixed we need to offset it by the visual
      // viewport's offset from the layout viewport origin.
      var offsetLeft = viewport.offsetLeft;
      var offsetTop = viewport.height
                  - layoutViewport.getBoundingClientRect().height
                  + viewport.offsetTop;

      // You could also do this by setting style.left and style.top if you
      // use width: 100% instead.
      bottomBar.style.transform = 'translate(' +
                                  offsetLeft + 'px,' +
                                  offsetTop + 'px) ' +
                                  'scale(' + 1/viewport.scale + ')'
    }
    window.visualViewport.addEventListener('scroll', viewportHandler);
    window.visualViewport.addEventListener('resize', viewportHandler);

**Note**: This technique should be used with care; emulating `position: device-fixed` in this way can result in the fixed element flickering during scrolling.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/visual-viewport/#the-visualviewport-interface">Visual Viewport API<br />
<span class="small">The definition of 'VisualViewport' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`VisualViewport`

61

79

63

No

48

13

61

61

68

63

45

13

8.0

`height`

61

79

63

No

48

13

61

61

68

63

45

13

8.0

`offsetLeft`

61

79

63

No

48

13

61

61

68

63

45

13

8.0

`offsetTop`

61

79

63

No

48

13

61

61

68

63

45

13

8.0

`onresize`

62

61

79

66

No

49

48

13

62

61

62

61

68

66

46

45

13

8.0

8.0

`onscroll`

62

61

79

66

No

49

48

13

62

61

62

61

68

66

46

45

13

8.0

8.0

`pageLeft`

61

79

63

No

48

13

61

61

68

63

45

13

8.0

`pageTop`

61

79

63

No

48

13

61

61

68

63

45

13

8.0

`resize_event`

62

61

79

66

No

49

48

13

62

61

62

61

68

66

46

45

13

8.0

8.0

`scale`

61

79

63

No

48

13

61

61

68

63

45

13

8.0

`scroll_event`

62

61

79

66

No

49

48

13

62

61

62

61

68

66

46

45

13

8.0

8.0

`width`

61

79

63

No

48

13

61

61

68

63

45

13

8.0

See also
--------

-   [Web Viewports Explainer](https://github.com/bokand/bokand.github.io/blob/master/web_viewports_explainer.md) — useful explanation of web viewports concepts, including the difference between visual viewport and layout viewport.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VisualViewport" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VisualViewport</a>
