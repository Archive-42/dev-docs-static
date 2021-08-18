Window: animationstart event
============================

The `animationstart` event is fired when a [CSS Animation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) has started. If there is an [`animation-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay), this event will fire once the delay period has expired. A negative delay will cause the event to fire with an [`elapsedTime`](../animationevent/elapsedtime) equal to the absolute value of the delay (and, correspondingly, the animation will begin playing at that time index into the sequence).

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../animationevent"><code>AnimationEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onanimationstart"><code>onanimationstart</code></a></td></tr></tbody></table>

The original target for this event is the `Element` that had the animation applied. You can listen for this event on the `Window` interface to handle it in the capture or bubbling phases. For full details on this event please see the page on [HTMLElement: animationstart](../htmlelement/animationstart_event).

Examples
--------

This listens for the `animationstart` event and logs a message when it is fired:

    window.addEventListener('animationstart', () => {
      console.log('Animation started');
    });

The same, but using `onanimationstart`:

    window.onanimationstart = () => {
      console.log('Animation started');
    };

[See a live example of this event.](../htmlelement/animationstart_event#live_example)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#eventdef-animationevent-animationstart">CSS Animations Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`animationstart_event`

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
-   Related events: [`animationend`](animationend_event), [`animationiteration`](animationiteration_event), [`animationcancel`](animationcancel_event)
-   This event on [`Document`](../document) targets: [`animationstart`](../document/animationstart_event)
-   This event on [`HTMLElement`](../htmlelement) targets: [`animationstart`](../htmlelement/animationstart_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/animationstart_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/animationstart_event</a>
