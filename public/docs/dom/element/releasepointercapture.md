# Element.releasePointerCapture()

The `releasePointerCapture()` method of the [`Element`](../element) interface releases (stops) _pointer capture_ that was previously set for a specific ([`PointerEvent`](../pointerevent)) _pointer_.

See the [`Element.setPointerCapture()`](setpointercapture) method for a description of _pointer capture_ and how to set it for a particular element.

## Syntax

    targetElement.releasePointerCapture(pointerId);

### Parameters

`pointerId`  
The [`pointerId`](../pointerevent/pointerid) of a [`PointerEvent`](../pointerevent) object.

### Return value

This method returns `undefined`.

### Exceptions

<table><thead><tr class="header"><th>Exception</th><th>Explanation</th></tr></thead><tbody><tr class="odd"><td><code>InvalidPointerId</code></td><td>pointerId does not match any of the active pointers.</td></tr></tbody></table>

## Example

This example sets pointer capture on a [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) when you press down on it. This lets you slide the element horizontally, even when you pointer moves outside of its boundaries.

### HTML

    <div id="slider">SLIDE ME</div>

### CSS

    div {
      width: 140px;
      height: 50px;
      display: flex;
      align-items: center;
      justify-content: center;
      background: #fbe;
    }

### JavaScript

    function beginSliding(e) {
      slider.onpointermove = slide;
      slider.setPointerCapture(e.pointerId);
    }

    function stopSliding(e) {
      slider.onpointermove = null;
      slider.releasePointerCapture(e.pointerId);
    }

    function slide(e) {
      slider.style.transform = `translate(${e.clientX - 70}px)`;
    }

    const slider = document.getElementById('slider');

    slider.onpointerdown = beginSliding;
    slider.onpointerup = stopSliding;

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#dom-element-releasepointercapture">Pointer Events – Level 2<br />
<span class="small">The definition of 'releasePointerCapture' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Non-stable version.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#widl-Element-releasePointerCapture-void-long-pointerId">Pointer Events<br />
<span class="small">The definition of 'releasePointerCapture' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`releasePointerCapture`

55

12

59

41

11

10

42

13

55

55

79

41

42

13

6.0

## See also

- [`Element.setPointerCapture()`](setpointercapture)
- [`Pointer Events`](../pointer_events)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/releasePointerCapture" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/releasePointerCapture</a>
