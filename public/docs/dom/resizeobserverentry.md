# ResizeObserverEntry

The `ResizeObserverEntry` interface represents the object passed to the [`ResizeObserver()`](resizeobserver/resizeobserver) constructor's callback function, which allows you to access the new dimensions of the [`Element`](element) or [`SVGElement`](svgelement) being observed.

## Properties

[`ResizeObserverEntry.borderBoxSize`](resizeobserverentry/borderboxsize) <span class="badge inline readonly">Read only </span>  
An object containing the new border box size of the observed element when the callback is run.

[`ResizeObserverEntry.contentBoxSize`](resizeobserverentry/contentboxsize) <span class="badge inline readonly">Read only </span>  
An object containing the new content box size of the observed element when the callback is run.

<span class="page-not-created">`ResizeObserverEntry.devicePixelContentBoxSize`</span> <span class="badge inline readonly">Read only </span>  
An object containing the new content box size in device pixels of the observed element when the callback is run.

[`ResizeObserverEntry.contentRect`](resizeobserverentry/contentrect) <span class="badge inline readonly">Read only </span>  
A [`DOMRectReadOnly`](domrectreadonly) object containing the new size of the observed element when the callback is run. Note that this is better supported than the above two properties, but it is left over from an earlier implementation of the Resize Observer API, is still included in the spec for web compat reasons, and may be deprecated in future versions.

[`ResizeObserverEntry.target`](resizeobserverentry/target) <span class="badge inline readonly">Read only </span>  
A reference to the [`Element`](element) or [`SVGElement`](svgelement) being observed.

**Note**: The content box is the box in which content can be placed, meaning the border box minus the padding and border width. The border box encompasses the content, padding, and border. See [The box model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model) for further explanation.

## Methods

None.

## Examples

The following snippet is taken from the [resize-observer-text.html](https://mdn.github.io/dom-examples/resize-observer/resize-observer-text.html) ([see source](https://github.com/mdn/dom-examples/blob/master/resize-observer/resize-observer-text.html)) example. This uses a simple feature detection test to see if the browser supports the newer `contentBoxSize` property — if so, it uses that to get the sizing data it needs. If not, it uses the older `contentRect` property.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/resize-observer/#resize-observer-entry-interface">Resize Observer<br />
<span class="small">The definition of 'ResizeObserverEntry' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ResizeObserverEntry`

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

`devicePixelContentBoxSize`

84

84

No

No

70

No

84

84

No

60

No

14.0

`target`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserverEntry" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserverEntry</a>
