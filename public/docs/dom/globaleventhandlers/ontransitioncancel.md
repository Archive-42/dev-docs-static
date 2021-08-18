# GlobalEventHandlers.ontransitioncancel

The `ontransitioncancel` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `transitioncancel` events.

The `transitioncancel` event is sent when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions) is cancelled. The transition is cancelled when:

- The value of the [`transition-property`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property) property that applies to the target is changed
- The [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) property is set to `"none"`.
- The transition is stopped before it has run to completion, e.g. by moving the mouse off a hover-transitioning element.

## Syntax

    var transitionCancelHandler = target.ontransitioncancel;

    target.ontransitioncancel = Function

### Value

A [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function) to be called when a `transitioncancel` event occurs indicating that a CSS transition has been cancelled on the `target`, where the target object is an HTML element ([`HTMLElement`](../htmlelement)), document ([`Document`](../document)), or window ([`Window`](../window)). The function receives as input a single parameter: a [`TransitionEvent`](../transitionevent) object describing the event which occurred; the event's [`TransitionEvent.elapsedTime`](../transitionevent/elapsedtime) property's value should be the same as the value of [`transition-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-duration).

**Note**: `elapsedTime` does not include time prior to the transition effect beginning; that means that the value of [`transition-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay) doesn't affect the value of `elapsedTime`, which is zero until the delay period ends and the animation begins.

## Example

In this example, we use the `transitionrun` and `transitionend` events to detect when the transition begins and ends, to cause a text update to occur during the transition. This could also be used to trigger animations or other effects, to allow chaining of reactions.

In addition, we also use a `click` event to make the box disappear (`display: none;`), showing how it triggers the `transitioncancel` event to fire.

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
      -webkit-transition: width 2s, height 2s, background-color 2s, -webkit-transform 2s, color 2s;
      transition: width 2s, height 2s, background-color 2s, transform 2s, color 2s;
    }

    .box:hover {
      background-color: #FFCCCC;
      color: #000000;
      width: 200px;
      height: 200px;
      -webkit-transform: rotate(180deg);
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

    box.onclick = function() {
      box.style.display = 'none';
      timeout = window.setTimeout(appear, 2000);
      function appear() {
        box.style.display = 'block';
      }
    }

    box.ontransitioncancel = function(event) {
      console.log('transitioncancel fired after ' + event.elapsedTime + ' seconds.');
    }

### Result

The resulting content looks like this:

Notice what happens when you hover your mouse cursor over the box, then move it away.

Also note the log that appears in the JavaScript console when you click the box, or move the cursor away before the transition has run to completion.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transitions/#dom-globaleventhandlers-ontransitioncancel">CSS Transitions<br />
<span class="small">The definition of 'ontransitioncancel' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`ontransitioncancel`

87

87

53

No

73

13.1

12

The event handler is exposed but will not actually be called unless both the "Web Animations" and "CSS Animations via Web Animations" preferences are enabled.

87

87

53

No

13.4

12

The event handler is exposed but will not actually be called unless both the "Web Animations" and "CSS Animations via Web Animations" preferences are enabled.

14.0

## See also

- The `transitioncancel` event this event handler is triggered by
- [`TransitionEvent`](../transitionevent)
- The `transitionrun` event, which occurs when the transition begins

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontransitioncancel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontransitioncancel</a>
