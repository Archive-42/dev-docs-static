# GlobalEventHandlers.onanimationcancel

The `onanimationcancel` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for processing `animationcancel` events.

An `animationcancel` event is sent when a [CSS animation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) unexpectedly aborts, that is, any time it stops running without sending an `animationend` event. This can happen, for example, when the [`animation-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name) is changed such that the animation is removed, or when the animating node is hidden—either directly or because any of its containing nodes are hidden—using CSS.

## Syntax

    var animCancelHandler = target.onanimationcancel;

    target.onanimationcancel = Function

### Value

A [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function) to be called when an `animationcancel` event occurs indicating that a CSS animation has begun on the _`target`_, where the target object is an HTML element ([`HTMLElement`](../htmlelement)), document ([`Document`](../document)), or window ([`Window`](../window)). The function receives as input a single parameter: an [`AnimationEvent`](../animationevent) object describing the event which occurred.

## Example

### HTML

    <div class="main">
      <div id="box" onanimationcancel="handleCancelEvent(event);">
        <div id="text">Box</div>
      </div>
    </div>

    <div class="button" id="toggleBox">
      Hide the Box
    </div>

    <pre id="log"></pre>

### CSS

Leaving out some bits of the CSS that don't matter for the discussion here, let's take a look at the styles for the box that we're animating. First is the box itself, with all its properties, including [`animation`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation), defined. We go ahead and describe the animation in-place here because the animation is intended to begin as soon as the page loads, rather than based on an event.

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
      animation: 5s ease-in-out 0s infinite alternate both slideBox;
    }

The animation's keyframes are described next, plotting a course from the top-left corner of the content box to the bottom-right corner.

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

Since the animation is described as taking place an infinite number of times, alternating direction each time, the box will glide back and forth between the two corners until stopped or the page is closed.

### JavaScript

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

Then we set up the `handleCancelEvent()` function, which is called in response to the `animationcancel` event, as set up in the HTML above. All we do here is log information to the console, but you might find other use cases, such as starting a new animation or effect, or terminating some dependent operation.

    function handleCancelEvent(event) {
      log("Animation canceled", event);
    };

Then we add a method to handle toggle [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) between ` "``flex" ` and ` "``none" ` and establish it as the handler for a `click` event on the "Hide/Show" the Box button:

    document.getElementById('toggleBox').addEventListener('click', function() {
      if (box.style.display == "none") {
        box.style.display = "flex";
        document.getElementById("toggleBox").innerHTML = "Hide the box";
      } else {
        box.style.display = "none";
        document.getElementById("toggleBox").innerHTML = "Show the box";
      }
    });

Toggling the box to `display: none` has the effect of aborting its animation. In browsers that support `animationcancel`, the event is fired and this handler is called.

### Result

Assembled together, you get this:

If your browser supports `animationcancel`, hiding the box using the button will cause a message to be displayed about the event.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#eventdef-animationevent-animationcancel">CSS Animations Level 1<br />
<span class="small">The definition of 'onanimationcancel' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`onanimationcancel`

No

No

54

?

?

13.1

12

The event handler is exposed but will not actually be called unless both the "Web Animations" and "CSS Animations via Web Animations" preferences are enabled.

No

No

54

?

13.4

12

The event handler is exposed but will not actually be called unless both the "Web Animations" and "CSS Animations via Web Animations" preferences are enabled.

No

## See also

- The `animationcancel` event this event handler is triggered by.
- [`AnimationEvent`](../animationevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationcancel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onanimationcancel</a>
