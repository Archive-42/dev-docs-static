ResizeObserverEntry.borderBoxSize
=================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `borderBoxSize` read-only property of the [`ResizeObserverEntry`](../resizeobserverentry) interface returns an array containing the new border box size of the observed element when the callback is run.

Syntax
------

    var myBorderBoxSize = ResizeObserverEntry.borderBoxSize;

### Value

An array containing objects with the new border box size of the observed element. The array is necessary to support elements that have multiple fragments, which occur in multi-column scenarios. Each object in the array contains two properties:

`blockSize`  
The length of the observed element's border box in the block dimension. For boxes with a horizontal [`writing-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode), this is the vertical dimension, or height; if the writing-mode is vertical, this is the horizontal dimension, or width.

`inlineSize`  
The length of the observed element's border box in the inline dimension. For boxes with a horizontal [`writing-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode), this is the horizontal dimension, or width; if the writing-mode is vertical, this is the vertical dimension, or height.

**Note**: For more explanation of writing modes and block and inline dimensions, read [Handling different text directions](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Handling_different_text_directions).

Examples
--------

    const resizeObserver = new ResizeObserver(entries => {
      for (let entry of entries) {
        if(entry.borderBoxSize && entry.borderBoxSize.length > 0) {
          entry.target.style.borderRadius = Math.min(100, (entry.borderBoxSize[0].inlineSize/10) +
                                                          (entry.borderBoxSize[0].blockSize/10)) + 'px';
        } else {
          entry.target.style.borderRadius = Math.min(100, (entry.contentRect.width/10) +
                                                          (entry.contentRect.height/10)) + 'px';
        }
      }
    });

    resizeObserver.observe(document.querySelector('div'));

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/resize-observer/#dom-resizeobserverentry-borderboxsize">Resize Observer<br />
<span class="small">The definition of 'borderBoxSize' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`borderBoxSize`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserverEntry/borderBoxSize" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserverEntry/borderBoxSize</a>
