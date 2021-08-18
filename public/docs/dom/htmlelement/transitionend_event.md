HTMLElement: transitionend event
================================

The `transitionend` event is fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) has completed. In the case where a transition is removed before completion, such as if the [`transition-property`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property) is removed or [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) is set to `none`, then the event will not be generated.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../transitionevent"><code>TransitionEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/ontransitionend"><code>ontransitionend</code></a></td></tr></tbody></table>

The `transitionend` event is fired in both directions - as it finishes transitioning to the transitioned state, and when it fully reverts to the default or non-transitioned state. If there is no transition delay or duration, if both are 0s or neither is declared, there is no transition, and none of the transition events are fired. If the `transitioncancel` event is fired, the `transitionend` event will not fire.

Examples
--------

This code gets an element that has a transition defined and adds a listener to the `transitionend` event:

    const transition = document.querySelector('.transition');

    transition.addEventListener('transitionend', () => {
      console.log('Transition ended');
    });

The same, but using the [`ontransitionend`](../globaleventhandlers/ontransitionend):

    const transition = document.querySelector('.transition');

    transition.ontransitionend = () => {
      console.log('Transition ended');
    };

### Live example

In the following example, we have a simple [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) element, styled with a transition that includes a delay:

    <div class="transition">Hover over me</div>
    <div class="message"></div>

    .transition {
      width: 100px;
      height: 100px;
      background: rgba(255,0,0,1);
      transition-property: transform background;
      transition-duration: 2s;
      transition-delay: 1s;
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

The `transitionend` event is fired in both directions: when the box finishes turning and the opacity hits 0 or 1, depending on the direction.

If there is no transition delay or duration, if both are 0s or neither is declared, there is no transition, and none of the transition events are fired.

If the `transitioncancel` event is fired, the `transitionend` event will not fire.

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

26

1

≤79

≤79

51

10

12.1

15

11.6-15

6.1

4

≤37

1

26

18

51

12.1

14

12-14

7

3.2

1.5

1.0

See also
--------

-   The [`GlobalEventHandlers.ontransitionend`](../globaleventhandlers/ontransitionend) event handler
-   The [`TransitionEvent`](../transitionevent) interface
-   CSS properties: [`transition`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition), [`transition-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay), [`transition-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-duration), [`transition-property`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property), [`transition-timing-function`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-timing-function)
-   Related events: [`transitionrun`](transitionrun_event), [`transitionstart`](transitionstart_event), [`transitioncancel`](transitioncancel_event)
-   This event on [`Document`](../document) targets: [`transitionend`](../document/transitionend_event)
-   This event on [`Window`](../window) targets: [`transitionend`](../window/transitionend_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/transitionend_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/transitionend_event</a>
