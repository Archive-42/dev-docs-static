Window: animationiteration event
================================

The `animationiteration` event is fired when an iteration of a [CSS Animation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) ends, and another one begins. This event does not occur at the same time as the [`animationend`](animationend_event) event, and therefore does not occur for animations with an `animation-iteration-count` of one.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../animationevent"><code>AnimationEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onanimationiteration"><code>onanimationiteration</code></a></td></tr></tbody></table>

The original target for this event is the [`Element`](../element) that had the animation applied. You can listen for this event on the [`Window`](../window) interface to handle it in the capture or bubbling phases. For full details on this event please see the page on [HTMLElement: animationiteration](../htmlelement/animationiteration_event).

Examples
--------

This code uses `animationiteration` to keep track of the number of iterations an animation has completed:

    let iterationCount = 0;

    window.addEventListener('animationiteration', () => {
      iterationCount++;
      console.log(`Animation iteration count: ${iterationCount}`);
    });

The same, but using the `onanimationiteration` event handler property:

    let iterationCount = 0;

    window.onanimationiteration = () => {
      iterationCount++;
      console.log(`Animation iteration count: ${iterationCount}`);
    };

[See a live example of this event.](../htmlelement/animationiteration_event#live_example)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#eventdef-animationevent-animationiteration">CSS Animations Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`animationiteration_event`

43

1

≤79

≤79

51

?

?

9

43

1

43

18

51

?

9

4.0

1.0

See also
--------

-   [CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations)
-   [Using CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
-   [`AnimationEvent`](../animationevent)
-   Related events: [`animationstart`](animationstart_event), [`animationend`](animationend_event), [`animationcancel`](animationcancel_event)
-   This event on [`Document`](../document) targets: [`animationiteration`](../document/animationiteration_event)
-   This event on [`HTMLElement`](../htmlelement) targets: [`animationiteration`](../htmlelement/animationiteration_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/animationiteration_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/animationiteration_event</a>
