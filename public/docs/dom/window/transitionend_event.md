Window: transitionend event
===========================

The `transitionend` event is fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) has completed. In the case where a transition is removed before completion, such as if the [`transition-property`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property) is removed or [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) is set to `none`, then the event will not be generated.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../transitionevent"><code>TransitionEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/ontransitionend"><code>ontransitionend</code></a></td></tr></tbody></table>

The `transitionend` event is fired in both directions - as it finishes transitioning to the transitioned state, and when it fully reverts to the default or non-transitioned state. If there is no transition delay or duration, if both are 0s or neither is declared, there is no transition, and none of the transition events are fired. If the `transitioncancel` event is fired, the `transitionend` event will not fire.

The original target for this event is the [`Element`](../element) that had the transition applied. You can listen for this event on the [`Window`](../window) interface to handle it in the capture or bubbling phases. For full details on this event please see the page on [HTMLElement: transitionend](../htmlelement/transitionend_event).

Examples
--------

This code adds a listener to the `transitionend` event:

    window.addEventListener('transitionend', () => {
      console.log('Transition ended');
    });

The same, but using the [`ontransitionend`](../globaleventhandlers/ontransitionend) property instead of `addEventListener()`:

    window.ontransitionend = () => {
      console.log('Transition ended');
    };

[See a live example of this event.](../htmlelement/transitionend_event#live_example)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transitions/#transitionend">CSS Transitions<br />
<span class="small">The definition of 'transitionend' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`transitionend_event`

No

No

51

?

?

Yes

No

No

51

?

Yes

No

See also
--------

-   The [`GlobalEventHandlers.ontransitionend`](../globaleventhandlers/ontransitionend) event handler
-   The [`TransitionEvent`](../transitionevent) interface
-   CSS properties: [`transition`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition), [`transition-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay), [`transition-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-duration), [`transition-property`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property), [`transition-timing-function`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-timing-function)
-   Related events: [`transitionrun`](../document/transitionrun_event), [`transitionstart`](../document/transitionstart_event), [`transitioncancel`](../document/transitioncancel_event)
-   This event on [`HTMLElement`](../htmlelement) targets: [`transitionend`](../htmlelement/transitionend_event)
-   This event on [`Document`](../document) targets: [`transitionend`](../document/transitionend_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/transitionend_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/transitionend_event</a>
