# GlobalEventHandlers.ontransitionend

The `ontransitionend` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `transitionend` events.

The `transitionend` event is sent to when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions) completes.

If the transition is removed from its target node before the transition completes execution, the `transitionend` event won't be generated. One way this can happen is by changing the value of the [`transition-property`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property) attribute which applies to the target. Another is if the [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) attribute is set to `none`.

## Syntax

    var transitionEndHandler = target.ontransitionend;

    target.ontransitionend = Function

### Value

A [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function) to be called when a `transitionend` event occurs indicating that a CSS transition has completed on the `target`, where the target object is an HTML element ([`HTMLElement`](../htmlelement)), document ([`Document`](../document)), or window ([`Window`](../window)). The function receives as input a single parameter: a [`TransitionEvent`](../transitionevent) object describing the event which occurred; the event's [`TransitionEvent.elapsedTime`](../transitionevent/elapsedtime) property's value should be the same as the value of [`transition-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-duration).

`elapsedTime` does not include time prior to the transition effect beginning; that means that the value of [`transition-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay) doesn't affect the value of `elapsedTime`, which is zero until the delay period ends and the animation begins.

## Example

In this example, we use the `transitionrun` and `transitionend` events to detect when the transition begins and ends, to cause a text update to occur during the transition. This could also be used to trigger animations or other effects, to allow chaining of reactions.

### HTML

This creates a [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) which we'll style with CSS below to make into a box that resizes and changes color and such.

    <div class="box"></div>

### CSS

The CSS below styles the box and applies a transition effect which makes the box's color and size change, and causes the box to rotate, while the mouse cursor hovers over it.

    .box {
      margin-left: 70px;
      margin-top: 30px;
      border-style: solid;
      border-width: 1px;
      display: block;
      width: 100px;
      height: 100px;
      background-color: #0000FF;
      color: #FFFFFF;
      padding: 20px;
      font: bold 1.6em "Helvetica", "Arial", sans-serif;
      transition: width 2s, height 2s, background-color 2s, transform 2s, color 2s;
    }

    .box:hover {
      background-color: #FFCCCC;
      color: #000000;
      width: 200px;
      height: 200px;
      transform: rotate(180deg);
    }

### JavaScript

Next, we need to establish our event handlers to change the text content of the box when the transition begins and ends.

    let box = document.querySelector(".box");
    box.ontransitionrun = function(event) {
      box.textContent = "Zooming...";
    }
    box.ontransitionend = function(event) {
      box.textContent = "Done!";
    }

### Result

The resulting content looks like this:

Notice what happens when you hover your mouse cursor over the box, then move it away.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transitions/#dom-globaleventhandlers-ontransitionend">CSS Transitions<br />
<span class="small">The definition of 'ontransitionend' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`ontransitionend`

79

Yes

18

≤79

51

No

66

11

79

Yes

79

Yes

51

57

11

11.0

Yes

## See also

- The `transitionend` event this event handler is triggered by
- [`TransitionEvent`](../transitionevent)
- The `transitionrun` event, which occurs when the transition begins

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontransitionend" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontransitionend</a>
