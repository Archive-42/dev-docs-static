ResizeObserverSize
==================

The `ResizeObserverSize` interface of the [`Resize Observer API`](resize_observer_api) is used by the [`ResizeObserverEntry`](resizeobserverentry) interface to access the box sizing properties of the element being observed.

**Note:**

In [multi-column layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Columns), which is a fragmented context, the sizing returned by `ResizeObserverSize` will be the size of the first column.

Properties
----------

 [`ResizeObserverSize.blockSize`](resizeobserversize/blocksize)<span class="badge inline readonly">Read only </span>   
The length of the observed element's border box in the block dimension. For boxes with a horizontal [`writing-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode), this is the vertical dimension, or height; if the writing-mode is vertical, this is the horizontal dimension, or width.

 [`ResizeObserverSize.inlineSize`](resizeobserversize/inlinesize)<span class="badge inline readonly">Read only </span>   
The length of the observed element's border box in the inline dimension. For boxes with a horizontal [`writing-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode), this is the horizontal dimension, or width; if the writing-mode is vertical, this is the vertical dimension, or height.

**Note:**

For more explanation of writing modes and block and inline dimensions, read [Handling different text directions](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Handling_different_text_directions).

Examples
--------

In this example the [`ResizeObserverEntry.contentBoxSize`](resizeobserverentry/contentboxsize) property returns a `ResizeObserverSize` object. This is an array containing the sizing information for the content box of the observed element.

    const resizeObserver = new ResizeObserver(entries => {
      for (let entry of entries) {
        console.log(entry.contentBoxSize[0]); // a ResizeObserverSize
      }
    });

    resizeObserver.observe(divElem);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/resize-observer/#resizeobserversize">Resize Observer<br />
<span class="small">The definition of 'ResizeObserverSize' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ResizeObserverSize`

84

84

?

No

Yes

No

84

84

?

Yes

No

14.0

`blockSize`

84

84

?

No

Yes

No

84

84

?

Yes

No

14.0

`inlineSize`

84

84

?

No

Yes

No

84

84

?

Yes

No

14.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserverSize" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserverSize</a>
