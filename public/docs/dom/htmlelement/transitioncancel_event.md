HTMLElement: transitioncancel event
===================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `transitioncancel` event is fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) is canceled.

See [`GlobalEventHandlers.ontransitioncancel`](../globaleventhandlers/ontransitioncancel) for more information.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../transitionevent"><code>TransitionEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/ontransitioncancel"><code>GlobalEventHandlers.ontransitioncancel</code></a></td></tr></tbody></table>

Examples
--------

This code gets an element that has a transition defined and adds a listener to the `transitioncancel` event:

    const transition = document.querySelector('.transition');

    transition.addEventListener('transitioncancel', () => {
      console.log('Transition canceled');
    });

The same, but using the [`ontransitioncancel`](../globaleventhandlers/ontransitioncancel) property instead of `addEventListener()`:

    const transition = document.querySelector('.transition');

    transition.ontransitioncancel = () => {
      console.log('Transition canceled');
    };

### Live example

In the following example, we have a simple [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) element, styled with a transition that includes a delay:

    <div class="transition"></div>
    <div class="message"></div>

    .transition {
      width: 100px;
      height: 100px;
      background: rgba(255,0,0,1);
      transition-property: transform background;
      transition-duration: 2s;
      transition-delay: 2s;
    }

    .transition:hover {
      transform: rotate(90deg);
      background: rgba(255,0,0,0);
    }

To this, we'll add some JavaScript to indicate that the `transitionstart`, `transitionrun`, `transitioncancel` and `transitionend` events fire. In this example, to cancel the transition, stop hovering over the transitioning box before the transition ends. For the transition end event to fire, stay hovered over the transition until the transition ends.

    const message = document.querySelector('.message');
    const el = document.querySelector('.transition');

    el.addEventListener('transitionrun', function() {
      message.textContent = 'transitionrun fired';
    });

    el.addEventListener('transitionstart', function() {
      message.textContent = 'transitionstart fired';
    });

    el.addEventListener('transitioncancel', function() {
      message.textContent = 'transitioncancel fired';
    });

    el.addEventListener('transitionend', function() {
      message.textContent = 'transitionend fired';
    });

The `transitioncancel` event is fired if the transition is cancelled in either direction after the `transitionrun` event occurs and before the `transitionend` is fired.

If there is no transition delay or duration, if both are 0s or neither is declared, there is no transition, and none of the transition events are fired.

If the `transitioncancel` event is fired, the `transitionend` event will not fire.

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

74

≤79

53

?

62

13.1

12

74

74

53

53

13.4

12

11.0

See also
--------

-   The [`GlobalEventHandlers.ontransitioncancel`](../globaleventhandlers/ontransitioncancel) event handler
-   The [`TransitionEvent`](../transitionevent) interface
-   CSS properties: [`transition`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition), [`transition-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay), [`transition-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-duration), [`transition-property`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property), [`transition-timing-function`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-timing-function)
-   Related events: [`transitionrun`](transitionrun_event), [`transitionstart`](transitionstart_event), [`transitionend`](transitionend_event)
-   This event on [`Document`](../document) targets: [`transitioncancel`](../document/transitioncancel_event)
-   This event on [`Window`](../window) targets: [`transitioncancel`](../window/transitioncancel_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/transitioncancel_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/transitioncancel_event</a>
