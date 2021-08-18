# Document: transitionstart event

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `transitionstart` event is fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) has actually started, i.e., after any [`transition-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay) has ended.

The difference is `transitionstart` and `transitionrun` is that `transitionrun` fires when the transition is created (i.e. at the start of any delay) and `transitionstart` fires when the actual animation has begun (i.e. at the end of any delay).

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../transitionevent"><code>TransitionEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><span class="page-not-created"><code>GlobalEventHandlers.ontransitionstart</code></span></td></tr></tbody></table>

The original target for this event is the [`Element`](../element) that had the transition applied. You can listen for this event on the [`Document`](../document) interface to handle it in the capture or bubbling phases. For full details on this event please see the page on [HTMLElement: transitionstart](../htmlelement/transitionstart_event).

## Examples

This code adds a listener to the `transitionstart` event:

    document.addEventListener('transitionstart', () => {
      console.log('Started transitioning');
    });

The same, but using the <span class="page-not-created">`ontransitionstart`</span> property instead of `addEventListener()`:

    document.ontransitionrun = () => {
      console.log('Started transitioning');
    };

[See a live example of this event.](../htmlelement/transitionstart_event#live_example)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transitions/#transitionstart">CSS Transitions<br />
<span class="small">The definition of 'transitionstart' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`transitionstart_event`

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

## See also

- The <span class="page-not-created">`GlobalEventHandlers.ontransitionstart`</span> event handler
- The [`TransitionEvent`](../transitionevent) interface
- CSS properties: [`transition`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition), [`transition-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay), [`transition-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-duration), [`transition-property`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property), [`transition-timing-function`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-timing-function)
- Related events: [`transitionend`](transitionend_event), [`transitionrun`](transitionrun_event), [`transitioncancel`](transitioncancel_event)
- This event on [`HTMLElement`](../htmlelement) targets: [`transitionstart`](../htmlelement/transitionstart_event)
- This event on [`Window`](../window) targets: [`transitionstart`](../window/transitionstart_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/transitionstart_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/transitionstart_event</a>
