Window: animationcancel event
=============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `animationcancel` event is fired when a [CSS Animation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) unexpectedly aborts. In other words, any time it stops running without sending an [`animationend`](animationend_event) event. This might happen when the [`animation-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name) is changed such that the animation is removed, or when the animating node is hidden using CSS. Therefore, either directly or because any of its containing nodes are hidden.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../animationevent"><code>AnimationEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onanimationcancel"><code>onanimationcancel</code></a></td></tr></tbody></table>

The original target for this event is the [`Element`](../element) that had the animation applied. You can listen for this event on the [`Window`](../window) interface to handle it in the capture or bubbling phases. For full details on this event please see the page on [HTMLElement: animationcancel](../htmlelement/animationcancel_event).

Examples
--------

This code adds a listener to the `animationcancel` event.

    window.addEventListener('animationcancel', () => {
      console.log('Animation canceled');
    });

The same, but using the [`onanimationcancel`](../globaleventhandlers/onanimationcancel) property instead of `addEventListener()`:

    window.onanimationcancel = () => {
      console.log('Animation canceled');
    };

[See a live example of this event.](../htmlelement/animationcancel_event#live_example)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#eventdef-animationevent-animationcancel">CSS Animations Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`animationcancel_event`

No

No

54

?

No

13.1

12

No

No

54

No

13.4

12

No

See also
--------

-   [CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations)
-   [Using CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
-   [`AnimationEvent`](../animationevent)
-   Related events: [`animationstart`](animationstart_event), [`animationend`](animationend_event), [`animationiteration`](animationiteration_event)
-   This event on [`Document`](../document) targets: [`animationcancel`](../document/animationcancel_event)
-   This event on [`HTMLElement`](../htmlelement) targets: [`animationcancel`](../htmlelement/animationcancel_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/animationcancel_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/animationcancel_event</a>
