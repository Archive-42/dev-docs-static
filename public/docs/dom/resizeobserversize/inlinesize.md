# ResizeObserverSize.inlineSize

The `inlineSize` read-only property of the [`ResizeObserverSize`](../resizeobserversize) interface returns the length of the observed element's border box in the inline dimension. For boxes with a horizontal [`writing-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode), this is the horizontal dimension, or width; if the writing-mode is vertical, this is the vertical dimension, or height.

**Note:**

For more explanation of writing modes and block and inline dimensions, read [Handling different text directions](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Handling_different_text_directions).

## Syntax

    var inlineSize = ResizeObserverSize.inlineSize;

### Value

A decimal representing the inline size in pixels.

## Examples

In this example we return an array of sizing information with [`ResizeObserverEntry.contentBoxSize`](../resizeobserverentry/contentboxsize). The `inlineSize` property returns the inline dimension size of the observed element.

    const resizeObserver = new ResizeObserver(entries => {
      for (let entry of entries) {
        let elemSize = entry.contentBoxSize[0];
        console.log(elemSize.inlineSize); // a decimal
      }
    });

    resizeObserver.observe(divElem);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/resize-observer/#dom-resizeobserversize-inlinesize">Resize Observer<br />
<span class="small">The definition of 'ResizeObserverEntry.inlineSize' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserverSize/inlineSize" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserverSize/inlineSize</a>
