VisualViewport: scroll event
============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `scroll` event of the `VisualViewport` interface is fired when the visual viewport is scrolled.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onscroll</code></td></tr></tbody></table>

Examples
--------

You can use the `scroll` event in an `addEventListener` method:

    visualViewport.addEventListener('scroll', function() {
      ...
    });

Or use the `onscroll` event handler property:

    visualViewport.onscroll = function() {
      ...
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/visual-viewport/#events">Visual Viewport API<br />
<span class="small">The definition of 'VisualViewport events' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

See also
--------

-   [Visual Viewport API homepage](../visual_viewport_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VisualViewport/scroll_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VisualViewport/scroll_event</a>
