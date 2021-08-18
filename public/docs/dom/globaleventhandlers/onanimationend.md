# GlobalEventHandlers.onanimationend

The `onanimationend` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for processing `animationend` events.

The `animationend` event fires when a [CSS animation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) reaches the end of its active period (which is calculated as `animation-duration` \* [`animation-iteration-count`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-iteration-count)) + [`animation-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay)).

## Syntax

    var animEndHandler = target.onanimationend;

    target.onanimationend = Function

### Value

A [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function) to be called when an `animationend` event occurs indicating that a CSS animation has ended on the _`target`_, where the target object is an HTML element ([`HTMLElement`](../htmlelement)), document ([`Document`](../document)), or window ([`Window`](../window)). The function receives as input a single parameter: an [`AnimationEvent`](../animationevent) object describing the event which occurred.

## Example

### CSS content

Leaving out some bits of the CSS that don't matter for the discussion here, let's take a look at the styles for the box that we're animating. First is the box itself. We set its size, position, color, and layout. Note that there's nothing there about animation. That's because we don't want the box to start animating right away. We'll add the [`animation`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation) style later to start animating the box.

    #box {
      width: var(--boxwidth);
      height: var(--boxwidth);
      left: 0;
      top: 0;
      border: 1px solid #7788FF;
      margin: 0;
      position: relative;
      background-color: #2233FF;
      display: flex;
      justify-content: center;
    }

The animation sequence is described next. First, the `"slideAnimation"` class, which establishes the [`animation`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation) that will cause the box to move over the course of five seconds, one time, using the `"slideBox"` keyframe set. The keyframes are defined next; they describe an animation which causes the box to migrate from the top-left corner of the container to the bottom-right corner.

    .slideAnimation {
      animation: 5s ease-in-out 0s 1 slideBox;
    }

    @keyframes slideBox {
      from {
        left:0;
        top:0;
      }
      to {
        left:calc(100% - var(--boxwidth));
        top:calc(100% - var(--boxwidth))
      }
    }

Since the CSS describes the animation but doesn't connect it to the box, we'll need some JavaScript code to do that. We'll get to that shortly.

### JavaScript content

Before we get to the animation code, we define a function which logs information to a box on the user's screen. We'll use this to show information about the events we receive. Note the use of [`AnimationEvent.animationName`](../animationevent/animationname) and [`AnimationEvent.elapsedTime`](../animationevent/elapsedtime) to get information about the event which occurred.

    function log(msg, event) {
      let logBox = document.getElementById("log");

      logBox.innerHTML += msg;

      if (event) {
        logBox.innerHTML += " <code>"+ event.animationName +
            "</code> at time " + event.elapsedTime.toFixed(2) +
            " seconds.";
      }

      logBox.innerHTML += "\n";
    };

Then we set up the event handlers for the `animationstart` and `animationend` events:

    let box = document.getElementById("box");

    box.onanimationstart = function(event) {
      log("Animation started", event);
    }

    box.onanimationend = function(event) {
      log("Animation stopped", event);
    };

Finally, we set up a handler for a click on the button that runs the animation:

    document.getElementById("play").addEventListener("click", function(event) {
      document.getElementById("box").className = "slideAnimation";
      event.target.style.display = "none";
    }, false);

This sets the class of the box we want to animate to the class that contains the [`animation`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation) description, then hides the play button because this example will only run the animation once. For information about why, and how to support running an animation more than once, see [Run an animation again](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Tips#run_an_animation_again) in [CSS Animations tips and tricks](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Tips).

### Result

Assembled together, you get this:

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#eventdef-animationevent-animationend">CSS Animations Level 1<br />
<span class="small">The definition of 'onanimationend' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`onanimationend`

79

Yes

18

≤79

51

No

66

9

79

Yes

79

Yes

51

57

9

12.0

Yes

## See also

- The `animationend` event, which triggers this event handler
- [`AnimationEvent`](../animationevent)
- The `animationstart` event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationend" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationend</a>
