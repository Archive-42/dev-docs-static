HTMLElement: transitionrun event
================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `transitionrun` event is fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) is first created, i.e. before any [`transition-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay) has begun.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../transitionevent"><code>TransitionEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><span class="page-not-created"><code>ontransitionrun</code></span></td></tr></tbody></table>

Examples
--------

This code adds a listener to the `transitionrun` event:

    el.addEventListener('transitionrun', () => {
      console.log('Transition is running but hasn\'t necessarily started transitioning yet');
    });

The same, but using the `ontransitionrun` property instead of `addEventListener()`:

    el.ontransitionrun = () => {
      console.log('Transition started running, and will start transitioning when the transition delay has expired');
    };

### Live example

In the following example, we have a simple [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) element, styled with a transition that includes a delay:

    <div class="transition">Hover over me</div>
    <div class="message"></div>

    .transition {
      width: 100px;
      height: 100px;
      background: rgba(255,0,0,1);
      transition-property: transform, background;
      transition-duration: 2s;
      transition-delay: 1s;
    }

    .transition:hover {
      transform: rotate(90deg);
      background: rgba(255,0,0,0);
    }

To this, we'll add some JavaScript to indicate where the [`transitionstart`](transitionstart_event) and [`transitionrun`](transitionrun_event) events fire.

    const el = document.querySelector('.transition');
    const message = document.querySelector('.message');

    el.addEventListener('transitionrun', function() {
      message.textContent = 'transitionrun fired';
    });

    el.addEventListener('transitionstart', function() {
      message.textContent = 'transitionstart fired';
    });

    el.addEventListener('transitionend', function() {
      message.textContent = 'transitionend fired';
    });

The difference is that:

-   `transitionrun` fires when the transition is created (i.e. at the start of any delay).
-   `transitionstart` fires when the actual animation has begun (i.e. at the end of any delay).

The `transitionrun` will occur even if the transition is canceled before the delay expires. If there is no transition delay or if transition-delay is negative, both `transitionrun` and `transitionstart` are fired.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transitions/#transitionrun">CSS Transitions<br />
<span class="small">The definition of 'transitionrun' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

-   The <span class="page-not-created">`GlobalEventHandlers.ontransitionrun`</span> event handler
-   The [`TransitionEvent`](../transitionevent) interface
-   CSS properties: [`transition`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition), [`transition-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay), [`transition-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-duration), [`transition-property`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property), [`transition-timing-function`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-timing-function)
-   Related events: [`transitionend`](transitionend_event), [`transitionstart`](transitionstart_event), [`transitioncancel`](transitioncancel_event)
-   This event on [`Document`](../document) targets: [`transitionrun`](../document/transitionrun_event)
-   This event on [`Window`](../window) targets: [`transitionrun`](../window/transitionrun_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/transitionrun_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/transitionrun_event</a>
