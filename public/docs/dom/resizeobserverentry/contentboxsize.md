ResizeObserverEntry.contentBoxSize
==================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `contentBoxSize` read-only property of the [`ResizeObserverEntry`](../resizeobserverentry) interface returns an array containing the new content box size of the observed element when the callback is run.

Syntax
------

    var myContentBoxSize = ResizeObserverEntry.contentBoxSize;

### Value

An object containing the new content box size of the observed element. This object contains two properties:

`blockSize`  
The length of the observed element's content box in the block dimension. For boxes with a horizontal [`writing-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode), this is the vertical dimension, or height; if the writing-mode is vertical, this is the horizontal dimension, or width.

`inlineSize`  
The length of the observed element's content box in the inline dimension. For boxes with a horizontal [`writing-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode), this is the horizontal dimension, or width; if the writing-mode is vertical, this is the vertical dimension, or height.

**Note**: For more explanation of writing modes and block and inline dimensions, read [Handling different text directions](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Handling_different_text_directions).

Examples
--------

The following snippet is taken from the [resize-observer-border-radius.html](https://mdn.github.io/dom-examples/resize-observer/resize-observer-border-radius.html) ([see source](https://github.com/mdn/dom-examples/blob/master/resize-observer/resize-observer-border-radius.html)) example. This example includes a green box, sized as a percentage of the viewport size. When the viewport size is changed, the box's rounded corners change in proportion to the size of the box. We could just implement this using [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) with a percentage, but that quickly leads to ugly-looking elliptical corners; this solution gives you nice square corners that scale with the box size.

    const resizeObserver = new ResizeObserver(entries => {
      for (let entry of entries) {
        if(entry.contentBoxSize) {
          entry.target.style.borderRadius = Math.min(100, (entry.contentBoxSize.inlineSize/10) +
                                                          (entry.contentBoxSize.blockSize/10)) + 'px';
        } else {
          entry.target.style.borderRadius = Math.min(100, (entry.contentRect.width/10) +
                                                          (entry.contentRect.height/10)) + 'px';
        }
      }
    });

    resizeObserver.observe(document.querySelector('div'));

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/resize-observer/#dom-resizeobserverentry-contentboxsize">Resize Observer<br />
<span class="small">The definition of 'contentBoxSize' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`contentBoxSize`

84

84

69

No

Yes

No

84

84

No

Yes

No

14.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserverEntry/contentBoxSize" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserverEntry/contentBoxSize</a>
