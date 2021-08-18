Visual Viewport API
===================

**Draft**

This page is not complete.

The **Visual Viewport API** provides an explicit mechanism for querying and modifying the properties of the window's [visual viewport](https://developer.mozilla.org/en-US/docs/Glossary/Visual_Viewport). The visual viewport is the visual portion of a screen excluding on-screen keyboards, areas outside of a pinch-zoom area, or any other on-screen artifact that doesn't scale with the dimensions of a page.

Visual Viewport concepts and usage
----------------------------------

The mobile web contains two viewports, the layout viewport and the visual viewport. The layout viewport covers all the elements on a page and the visual viewport is what is actually visible on the screen. When the user pinch-zooms into the page, the visual viewport shrinks but the layout viewport is unchanged. User-interface features like the on-screen keyboard (OSK) can shrink the visual viewport without affecting the layout viewport.

What happens when a web page element needs to be visible on screen regardless of the visible portion of a web page? For example, what if you need a set of image controls to remain on screen regardless of the pinch zoom level of the device? Current browsers vary in how they handle this. The visual viewport lets web developers solve this by positioning elements relative to what's shown on screen.

To access a window's visual viewport, you can obtain a [`VisualViewport`](visualviewport) object from the [`window.visualViewport`](window/visualviewport) property. The object includes a set of properties describing the viewport. It also adds two events, `onresize` and `onscroll`, that fire whenever the visual viewport changes. These events allow you to position elements relative to the visual viewport that would normally be anchored to the layout viewport.

Accessing the API
-----------------

 [`window.visualViewport`](window/visualviewport) <span class="badge inline readonly">Read only </span>   
A read-only reference to the window's [`VisualViewport`](visualviewport) object. If this property doesn't exist, the API is unsupported.

Interfaces
----------

[`VisualViewport`](visualviewport)  
Represents the visual viewport for a given window. A window's `VisualViewport` object provides information about the viewport's position and size, and receives the [`resize`](visualviewport/resize_event) and [`scroll`](visualviewport/scroll_event) events you can monitor to know when changes occur to the window's viewport.

Example
-------

The code below is based on the sample the specification, though it adds a few things that make it function better. It shows a function called `viewportHandler()`. When called it queries the `offsetLeft` and `height` properties for values it uses in a CSS `translate()` method. You invoke this function by passing it to *both* event calls.

One thing that may not be clear in this example is the use of the `pendingUpdate` flag and the call to `requestAnimationFrame()`. The `pendingUpdate` flag serves to prevent multiple invocations of the transfrom that can occur when `onresize` and `onscroll` fire at the same time. Using `requestAnimationFrame()` ensures that the transform occurs before the next render.

    let pendingUpdate = false;

    function viewportHandler(event) {
      if (pendingUpdate) return;
      pendingUpdate = true;

      requestAnimationFrame(() => {
        pendingUpdate = false;
        var layoutViewport = document.getElementById('layoutViewport');

        // Since the bar is position: fixed we need to offset it by the
        // visual viewport's offset from the layout viewport origin.
        var viewport = event.target;
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
        })
    }

    window.visualViewport.addEventListener('scroll', viewportHandler);
    window.visualViewport.addEventListener('resize', viewportHandler);

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

`Visual_Viewport_API`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Visual_Viewport_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Visual_Viewport_API</a>
