# ResizeObserverEntry.contentRect

The `contentRect` read-only property of the [`ResizeObserverEntry`](../resizeobserverentry) interface returns a [`DOMRectReadOnly`](../domrectreadonly) object containing the new size of the observed element when the callback is run. Note that this is better supported than [`ResizeObserverEntry.borderBoxSize`](borderboxsize) or [`ResizeObserverEntry.contentBoxSize`](contentboxsize), but it is left over from an earlier implementation of the Resize Observer API, is still included in the spec for web compat reasons, and may be deprecated in future versions.

## Syntax

    var contentRect = resizeObserverEntry.contentRect;

### Value

A [`DOMRectReadOnly`](../domrectreadonly) object containing the new size of the element indicated by the [`target`](target) property.

If the `target` is an HTML [`Element`](../element), the returned `contentRect` is the element's content box. If the `target` is an [`SVGElement`](../svgelement), the returned `contentRect` is the SVG's bounding box.

## Examples

The following snippet is taken from the [resize-observer-text.html](https://mdn.github.io/dom-examples/resize-observer/resize-observer-text.html) ([see source](https://github.com/mdn/dom-examples/blob/master/resize-observer/resize-observer-text.html)) example. This uses a simple feature detection test to see if the browser supports the newer [`ResizeObserverEntry.contentBoxSize`](contentboxsize) property — if so, it uses that to get the sizing data it needs. If not, it uses `contentRect`.

    const resizeObserver = new ResizeObserver(entries => {
      for (let entry of entries) {
        if(entry.contentBoxSize) {
          h1Elem.style.fontSize = Math.max(1.5, entry.contentBoxSize.inlineSize/200) + 'rem';
          pElem.style.fontSize = Math.max(1, entry.contentBoxSize.inlineSize/600) + 'rem';
        } else {
          h1Elem.style.fontSize = Math.max(1.5, entry.contentRect.width/200) + 'rem';
          pElem.style.fontSize = Math.max(1, entry.contentRect.width/600) + 'rem';
        }
      }
    });

    resizeObserver.observe(divElem);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/resize-observer/#dom-resizeobserverentry-contentrect">Resize Observer<br />
<span class="small">The definition of 'contentRect' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`contentRect`

64

79

69

No

Yes

No

64

64

No

Yes

No

9.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserverEntry/contentRect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserverEntry/contentRect</a>
