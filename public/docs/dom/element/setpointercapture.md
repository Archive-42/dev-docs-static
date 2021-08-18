Element.setPointerCapture()
===========================

The `setPointerCapture()` method of the [`Element`](../element) interface is used to designate a specific element as the *capture target* of future pointer events. Subsequent events for the pointer will be targeted at the capture element until capture is released (via [`Element.releasePointerCapture()`](releasepointercapture) or the [`pointerup`](../htmlelement/pointerup_event) event is fired).

**Note:** When pointer capture is set, [`pointerover`](../htmlelement/pointerover_event), [`pointerout`](../htmlelement/pointerout_event), [`pointerenter`](../htmlelement/pointerenter_event), and [`pointerleave`](../htmlelement/pointerleave_event) events are only generated when crossing the boundary of the capture target. This has the effect of suppressing these events on all other elements.

### Overview of pointer capture

*Pointer capture* allows events for a particular *pointer event* ([`PointerEvent`](../pointerevent)) to be re-targeted to a particular element instead of the normal (or *hit test*) target at a pointer's location. This can be used to ensure that an element continues to receive pointer events even if the pointer device's contact moves off the element (such as by scrolling or panning).

Syntax
------

    targetElement.setPointerCapture(pointerId);

### Parameters

`pointerId`  
The [`pointerId`](../pointerevent/pointerid) of a [`PointerEvent`](../pointerevent) object.

### Return value

This method returns [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

### Exceptions

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Exception</th><th>Explanation</th></tr></thead><tbody><tr class="odd"><td><code>NotFoundError</code></td><td><code>pointerId</code> does not match any of the active pointers.<div class="note notecard"><strong>Note:</strong> Firefox versions <em>before</em> Firefox 82 incorrectly throw <code>InvalidPointerId</code>.</div></td></tr></tbody></table>

Example
-------

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

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#dom-element-setpointercapture">Pointer Events – Level 2<br />
<span class="small">The definition of 'setPointerCapture' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Non-stable version.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#widl-Element-setPointerCapture-void-long-pointerId">Pointer Events<br />
<span class="small">The definition of 'setPointerCapture' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`setPointerCapture`

55

12

59

Before Firefox 82, `setPointerCapture()` throws `InvalidPointerId` for an invalid `pointerId` argument. From Firefox 82, it throws [the specified](https://w3c.github.io/pointerevents/#setting-pointer-capture) `NotFoundError` exception. See [bug 1662124](https://bugzil.la/1662124).

41

11

10

42

13

55

55

79

Before Firefox 82, `setPointerCapture()` throws `InvalidPointerId` for an invalid `pointerId` argument. From Firefox 82, it throws [the specified](https://w3c.github.io/pointerevents/#setting-pointer-capture) `NotFoundError` exception. See [bug 1662124](https://bugzil.la/1662124).

41

42

13

6.0

See also
--------

-   [`Element.releasePointerCapture`](releasepointercapture)
-   [`Pointer Events`](../pointer_events)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/setPointerCapture" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/setPointerCapture</a>
