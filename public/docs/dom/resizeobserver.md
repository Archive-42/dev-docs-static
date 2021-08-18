# ResizeObserver

The `ResizeObserver` interface reports changes to the dimensions of an [`Element`](element)'s content or border box, or the bounding box of an [`SVGElement`](svgelement).

**Note**: The content box is the box in which content can be placed, meaning the border box minus the padding and border width. The border box encompasses the content, padding, and border. See [The box model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model) for further explanation.

`ResizeObserver` avoids infinite callback loops and cyclic dependencies that are often created when resizing via a callback function. It does this by only processing elements deeper in the DOM in subsequent frames. Implementations should, if they follow the specification, invoke resize events before paint and after layout.

## Constructor

[`ResizeObserver()`](resizeobserver/resizeobserver)  
Creates and returns a new `ResizeObserver` object.

## Properties

None.

## Methods

[`ResizeObserver.disconnect()`](resizeobserver/disconnect)  
Unobserves all observed [`Element`](element) targets of a particular observer.

[`ResizeObserver.observe()`](resizeobserver/observe)  
Initiates the observing of a specified [`Element`](element).

[`ResizeObserver.unobserve()`](resizeobserver/unobserve)  
Ends the observing of a specified [`Element`](element).

## Examples

In the [resize-observer-text.html](https://mdn.github.io/dom-examples/resize-observer/resize-observer-text.html) ([see source](https://github.com/mdn/dom-examples/blob/master/resize-observer/resize-observer-text.html)) example, we use the resize observer to change the [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size) of a header and paragraph as a slider’s value is changed causing the containing `<div>` to change width. This shows that you can respond to changes in an element’s size, even if they have nothing to do with the viewport.

We also provide a checkbox to turn the observer off and on. If it is turned off, the text will not change in response to the `<div>`'s width changing.

The JavaScript looks like so:

    const h1Elem = document.querySelector('h1');
    const pElem = document.querySelector('p');
    const divElem = document.querySelector('body > div');
    const slider = document.querySelector('input[type="range"]');
    const checkbox = document.querySelector('input[type="checkbox"]');

    divElem.style.width = '600px';

    slider.addEventListener('input', () => {
      divElem.style.width = slider.value + 'px';
    })

    const resizeObserver = new ResizeObserver(entries => {
      for (let entry of entries) {
        if(entry.contentBoxSize) {
          // Firefox implements `contentBoxSize` as a single content rect, rather than an array
          const contentBoxSize = Array.isArray(entry.contentBoxSize) ? entry.contentBoxSize[0] : entry.contentBoxSize;

          h1Elem.style.fontSize = Math.max(1.5, contentBoxSize.inlineSize / 200) + 'rem';
          pElem.style.fontSize = Math.max(1, contentBoxSize.inlineSize / 600) + 'rem';
        } else {
          h1Elem.style.fontSize = Math.max(1.5, entry.contentRect.width / 200) + 'rem';
          pElem.style.fontSize = Math.max(1, entry.contentRect.width / 600) + 'rem';
        }
      }

      console.log('Size changed');
    });

    resizeObserver.observe(divElem);

    checkbox.addEventListener('change', () => {
      if (checkbox.checked) {
        resizeObserver.observe(divElem);
      } else {
        resizeObserver.unobserve(divElem);
      }
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/resize-observer/#resize-observer-interface">Resize Observer<br />
<span class="small">The definition of 'ResizeObserver' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ResizeObserver`

64

79

69

No

51

13.1

64

64

79

47

13.4

9.0

`ResizeObserver`

64

79

69

No

51

13.1

64

64

79

47

13.4

9.0

`disconnect`

64

79

69

No

51

13.1

64

64

79

47

13.4

9.0

`observe`

64

79

69

No

51

13.1

64

64

79

47

13.4

9.0

`unobserve`

64

79

69

No

51

13.1

64

64

79

47

13.4

9.0

## See also

- [The box model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model)
- [`PerformanceObserver`](performanceobserver)
- [`IntersectionObserver`](intersectionobserver) (part of the [Intersection Observer API](intersection_observer_api))

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserver</a>
