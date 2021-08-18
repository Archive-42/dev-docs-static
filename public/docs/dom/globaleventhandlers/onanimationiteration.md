GlobalEventHandlers.onanimationiteration
========================================

**Draft**

This page is not complete.

The `onanimationiteration` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for processing `animationiteration` events.

The `animationiteration` event is sent when a [CSS animation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) reaches the end of an iteration. An iteration ends when a single pass through the sequence of animation instructions is completed by executing the last animation step.

Syntax
------

    var animIterationHandler = target.onanimationiteration;

    target.onanimationiteration = Function

### Value

A [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function) to be called when an `animationiteration` event occurs indicating that a CSS animation has reached the end of an iteration while running on the *`target`*, where the target object is an HTML element ([`HTMLElement`](../htmlelement)), document ([`Document`](../document)), or window ([`Window`](../window)). The function receives as input a single parameter: an [`AnimationEvent`](../animationevent) object describing the event which occurred.

Example
-------

Let's create an animation which automatically pauses at the end of each iteration, allowing the user to choose whether or not to start the next iteration. Much of this code is the same as in other examples of animation events, so it may look familiar.

### CSS

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
      animation: 2s ease-in-out 0s infinite alternate both paused slideBox;
    }

The animation's keyframes are defined next; they describe an animation which causes the box to migrate from the top-left corner of the container to the bottom-right corner.

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

### JavaScript

Some JavaScript code will need to be written to handle the click on the button to start the next iteration. Let's have a look.

    var box = document.getElementById("box");
    var iterationCounter = 0;

    box.onanimationiteration = function(event) {
      box.style.animationPlayState = "paused";
      document.getElementById("play").innerHTML = "Start Iteration #" + (iterationCounter+1);
    };

This sets up two global variables: `box`, which references the `"box"` element that we're animating, and `iterationCounter`, which is initially zero, which indicates how many iterations of the animation have occurred.

The onanimationiteration event handler is then set up. It sets the box's [`animation-play-state`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-play-state) to "paused", then updates the text displayed in the button to indicate that clicking the button will start playing the next iteration of the animation.

Finally, we set up a handler for a click on the button that runs the animation:

    document.getElementById("play").addEventListener("click", function(event) {
      box.style.animationPlayState = "running";
      iterationCounter++;
    }, false);

This sets the box element's [`animation-play-state`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-play-state) to "running" and increments the iteration counter. That's all there is to it!

### Result

Assembled together, you get this:

Each time the box reaches the opposing corner, it stops, with the button reflecting which iteration number is up next, until you click the button to run the next iteration.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#eventdef-animationevent-animationiteration">CSS Animations Level 1<br />
<span class="small">The definition of 'onanimationiteration' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`onanimationiteration`

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

See also
--------

-   The `animationiteration` event, which triggers this event handler
-   [`AnimationEvent`](../animationevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationiteration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationiteration</a>
