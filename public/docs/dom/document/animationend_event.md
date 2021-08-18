# Document: animationend event

The `animationend` event is fired when a [CSS Animation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) has completed. If the animation aborts before reaching completion, such as if the element is removed from the DOM or the animation is removed from the element, the `animationend` event is not fired.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../animationevent"><code>AnimationEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onanimationend"><code>onanimationend</code></a></td></tr></tbody></table>

The original target for this event is the [`Element`](../element) that had the animation applied. You can listen for this event on the [`Document`](../document) interface to handle it in the capture or bubbling phases. For full details on this event please see the page on [HTMLElement: animationend](../htmlelement/animationend_event).

## Examples

This example listens for the `animationend` event:

    document.addEventListener('animationend', () => {
      console.log('Animation ended');
    });

The same, but using the `onanimationend` event handler property:

    document.onanimationend = () => {
      console.log('Animation ended');
    };

[See a live example of this event.](../htmlelement/animationend_event#live_example)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#eventdef-animationevent-animationend">CSS Animations Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`animationend_event`

43

12

Yes

10

30

9

43

43

Yes

30

9

4.0

## See also

- [CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations)
- [Using CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
- [`AnimationEvent`](../animationevent)
- Related events: [`animationstart`](animationstart_event), [`animationcancel`](animationcancel_event), [`animationiteration`](animationiteration_event)
- This event on [`Window`](../window) targets: [`animationend`](../window/animationend_event)
- This event on [`HTMLElement`](../htmlelement) targets: [`animationend`](../htmlelement/animationend_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/animationend_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/animationend_event</a>
