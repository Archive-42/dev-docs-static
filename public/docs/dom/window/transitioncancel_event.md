Window: transitioncancel event
==============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `transitioncancel` event is fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) is canceled.

See [`GlobalEventHandlers.ontransitioncancel`](../globaleventhandlers/ontransitioncancel) for more information.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../transitionevent"><code>TransitionEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/ontransitioncancel"><code>GlobalEventHandlers.ontransitioncancel</code></a></td></tr></tbody></table>

The original target for this event is the [`Element`](../element) that had the transition applied. You can listen for this event on the [`Window`](../window) interface to handle it in the capture or bubbling phases. For full details on this event please see the page on [HTMLElement: transitioncancel](../htmlelement/transitioncancel_event).

Examples
--------

This code adds a listener to the `transitioncancel` event:

    window.addEventListener('transitioncancel', () => {
      console.log('Transition canceled');
    });

The same, but using the [`ontransitioncancel`](../globaleventhandlers/ontransitioncancel) property instead of `addEventListener()`:

    window.ontransitioncancel = () => {
      console.log('Transition canceled');
    };

[See a live example of this event.](../htmlelement/transitioncancel_event#live_example)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transitions/#transitioncancel">CSS Transitions<br />
<span class="small">The definition of 'transitioncancel' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`transitioncancel_event`

No

No

53

?

?

13.1

12

No

No

53

?

13.4

12

No

See also
--------

-   The [`GlobalEventHandlers.ontransitioncancel`](../globaleventhandlers/ontransitioncancel) event handler
-   The [`TransitionEvent`](../transitionevent) interface
-   CSS properties: [`transition`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition), [`transition-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay), [`transition-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-duration), [`transition-property`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property), [`transition-timing-function`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-timing-function)
-   Related events: [`transitionrun`](transitionrun_event), [`transitionstart`](transitionstart_event), [`transitionend`](transitionend_event)
-   This event on [`HTMLElement`](../htmlelement) targets: [`transitioncancel`](../htmlelement/transitioncancel_event)
-   This event on [`Document`](../document) targets: [`transitioncancel`](../document/transitioncancel_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/transitioncancel_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/transitioncancel_event</a>
