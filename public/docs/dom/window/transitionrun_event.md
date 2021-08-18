Window: transitionrun event
===========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `transitionrun` event is fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) is first created, i.e. before any [`transition-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay) has begun.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../transitionevent"><code>TransitionEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>ontransitionrun</code></td></tr></tbody></table>

The original target for this event is the `Element` that had the transition applied. You can listen for this event on the `Window` interface to handle it in the capture or bubbling phases. For full details on this event please see the page on [HTMLElement: transitionrun](../htmlelement/transitionrun_event).

Examples
--------

This code adds a listener to the `transitionrun` event:

    window.addEventListener('transitionrun', () => {
      console.log('Transition is running but hasn't necessarily started transitioning yet');
    });

The same, but using the `ontransitionrun` property instead of `addEventListener()`:

    window.ontransitionrun = () => {
      console.log('Transition started running');
    };

[See a live example of this event.](../htmlelement/transitionrun_event#live_example)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transitions/#transitionrun">CSS Transitions<br />
<span class="small">The definition of 'transitionrun' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`transitionrun_event`

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

-   The <span class="page-not-created">`GlobalEventHandlers.ontransitionrun`</span> event handler
-   The [`TransitionEvent`](../transitionevent) interface
-   CSS properties: [`transition`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition), [`transition-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay), [`transition-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-duration), [`transition-property`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property), [`transition-timing-function`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-timing-function)
-   Related events: `transitionend`, `transitionstart`, `transitioncancel`
-   This event on `HTMLElement` targets: `transitionrun`
-   This event on `Document` targets: `transitionrun`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/transitionrun_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/transitionrun_event</a>
