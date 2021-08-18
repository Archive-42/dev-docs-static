# EffectTiming.fill

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The [Web Animations API](../web_animations_api)'s [`EffectTiming`](../effecttiming) dictionary's `fill` property specifies a **fill mode**, which defines how the element to which the animation is applied should look when the animation sequence is not actively running, such as before the time specified by [`iterationStart`](iterationstart) or after animation's end time.

For example, setting fill to `"none"` means the animation's effects are not applied to the element if the current time is outside the range of times during which the animation is running, while `"forwards"` ensures that once the animation's end time has been passed, the element will continue to be drawn in the state it was in at its last rendered frame.

Note that authors are discouraged from using fill modes to persist the effect of an animation indefinitely. See the [alternatives to fill modes section below](#alternatives_to_fill_modes) for approaches that are simpler and more performant.

[`Element.animate()`](../element/animate), and [`KeyframeEffect()`](../keyframeeffect/keyframeeffect) accept an object of timing properties including `fill.` The value of `fill` corresponds directly to [`fill`](fill) in [`EffectTiming`](../effecttiming) objects returned by [`getTiming()`](../animationeffect/gettiming) in [`AnimationEffect`](../animationeffect) and [`KeyframeEffect`](../keyframeeffect).

## Syntax

    var timingProperties = {
      fill: "none" | "forwards" | "backwards" | "both" | "auto"
    }

### Value

A [`DOMString`](../domstring) indicating the fill type to use in order to properly render an affected element when outside the animation's **active interval** (that is, when it's not actively animating). The default is `"auto"`.

`"none"`  
The animation's effects are only visible while the animation is iterating or its playhead is positioned over an iteration. The animation's effects are not visible when its [`playState`](../animation/playstate) is `pending` with a <span class="page-not-created">`delay`</span>, when its `playState` is `finished`, or during its <span class="page-not-created">`endDelay`</span> or <span class="page-not-created">`delay`</span>. In other words, if the animation isn't in its active interval, the affected element is not visible.

`"forwards"`  
The affected element will continue to be rendered in the state of the final animation framecontinue to be applied to the after the animation has completed playing, in spite of and during any <span class="page-not-created">`endDelay`</span> or when its `playState` is `finished`.

`"backwards"`  
The animation's effects should be reflected by the element(s) state prior to playing, in spite of and during any <span class="page-not-created">`delay`</span> and `pending` [`playState`](../animation/playstate).

`"both"`  
Combining the effects of **both** `forwards` and `backwards`: The animation's effects should be reflected by the element(s) state prior to playing and retained after the animation has completed playing, in spite of and during any <span class="page-not-created">`endDelay`</span>, <span class="page-not-created">`delay`</span> and/or `pending` or `finished` [`playState`](../animation/playstate).

`"auto"`  
If the animation effect the fill mode is being applied to is a keyframe effect ([`KeyframeEffect`](../keyframeeffect) or [`KeyframeEffectReadOnly`](../keyframeeffect)), `"auto"` is equivalent to `"none"`. Otherwise, the result is `"both"`.

## Examples

Here are a few examples.

### Fill mode: none

#### HTML content

The HTML is pretty simple. We have a [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) named `"main"` which is a container for the element we'll be animating, which is a `<div>` with the ID `"box"`. Below that, another `<div>` serves as a button that will trigger the animation to begin.

    <div class="main">
      <div id="box">
        <div id="text">Look! A box!</div>
      </div>
    </div>
    <div class="button" id="animateButton">
      Animate!
    </div>

While there's other CSS involved in this example, the part that really matters for our purposes is the CSS that styles the `"box"` element that we'll be animating. That CSS looks like this:

    #box {
      width: 200px;
      height: 200px;
      left: 50px;
      top: 50px;
      border: 1px solid #7788FF;
      margin: 0;
      position: relative;
      background-color: #2233FF;
      display: flex;
      justify-content: center;
    }

All this does is specify the size, border, and color information, as well as indicate that the box should be centered both vertically and horizontally inside its container. Note that there's no rotation applied.

#### JavaScript content

Now let's check out the JavaScript. First we'll define the two objects that describe the keyframes and the timing configuration to use, then we'll actually see the code that triggers and runs the animation when the `"animateButton"` button is clicked.

    var boxRotationKeyframes = [
      { transform: "rotate(-90deg)" },
      { transform: "rotate(90deg)" }
    ];

The `boxRotationKeyframes` object is an array of keyframes, each describing the state of the affected element at a point in the animation process. In this case, we have just two keyframes; the first defines what affect is applied to the element _immediately after the animation first begins to play_, and the second defines the effect applied to the element in the _last moment before it ends_. Those phrases are crucial. Let's look at why.

The first keyframe says that when the animation begins, the element should be rotated 90° to the left. That means that unless we specify otherwise using the `fill` property, the instant the animation is started the element will be rotated to the left 90°, and then it will animate smoothly from there. Since by default the box isn't rotated,

The last keyframe says that the animation's final frame should draw the animation rotated 90° to the right from its original orientation.

    var boxRotationTiming = {
      duration: 2000,
      iterations: 1,
      fill: "none"
    };

The `boxRotationTiming` object describes how long the animation should take to run, how many times it should run, what state the element should be in before the animation begins and after it ends, and so forth.

Here we specify that the animation should take 2000 milliseconds (2 seconds) to complete, should only run once, and that the fill mode should be `"none"`. As defined above, the `"none"` fill mode means that the element will be rendered in its natural, unaltered condition anytime the animation isn't actively running.

    document.getElementById("animateButton").addEventListener("click", event => {
      document.getElementById("box").animate(
        boxRotationKeyframes,
        boxRotationTiming
      );
    }, false);

The rest of the code is pretty simple: it adds an event listener to the "Animate" button so that when it's clicked by the user, the box is animated by calling [`Element.animate()`](../element/animate) on it, providing the `boxRotationKeyframes` and `boxRotationTiming` objects to describe the animation that should occur.

### Result

Below we see what the result looks like. Notice how before the animation starts running, the box is upright, then upon clicking the "Animate!" button, the box is instantly rotated 90° to the left (to correspond to the first keyframe in the animation sequence). Then, when the animation finishes running, the box instantaneously leaps back to its original state and is upright once again.

Give it a try below!

### Follow the White Rabbit example

In the [Follow the White Rabbit](https://codepen.io/rachelnabors/pen/eJyWzm?editors=0010) example, the White Rabbit's animation is formed by coupling a `KeyframeEffect` with an `Animation` object. The `keyframeEffect` takes an object of [timing properties](../effecttiming), which is where we pass in `fill`. `Forwards` makes the rabbit retain its last keyframe rather than reverting to its unanimated state:

    // Create a set of keyframes to slide the rabbit down the hole--and keep him down with 'fill'!
    var rabbitDownKeyframes = new KeyframeEffect(
      whiteRabbit,
      [
        { transform: 'translateY(0%)' },
        { transform: 'translateY(100%)' }
      ], {
        duration: 3000,
        fill: 'forwards'
      }
    );

    // Set up the rabbit's animation to play on command by calling rabbitDownAnimation.play() later
    var rabbitDownAnimation = new Animation(rabbitDownKeyframes, document.timeline);

## Alternatives to fill modes

Fill modes are primarily provided as a means of representing the [animation-fill-mode](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-fill-mode) feature of CSS animations. When used to persist the effect of an animation indefinitely, however, they have a number of drawbacks:

- The forwards fill of an animation (or backwards fill if the animation is playing in reverse) will continue to override any changes to specified style indefinitely which can lead to confusing behavior. This is because animations take priority in the [CSS cascade](https://developer.mozilla.org/en-US/docs/Web/CSS/Cascade#cascading_order) over normal author styles.
- In order to avoid leaking memory when many filling animations overlap, the browser is required to remove overlapped animations which can lead to surprising results in some cases.

Rather than using fill modes to persist an animation, it is often simpler to set the final value of the animation effect directly in specified style:

    elem.animate({ transform: 'translateY(100px)' }, 200).finished.then(() => {
      elem.style.transform = 'translateY(100px)';
    });

Alternatively, it may be simpler still to set the final value in specified style before triggering the animation and then animate _from_ the start value. This is the approach used in [FLIP animation](https://aerotwist.com/blog/flip-your-animations/).

    elem.style.transform = 'translateY(100px)';
    elem.animate({ transform: 'none', offset: 0 }, 200);

For some complex effects where animations layer on top of one another, it may be necessary to use a fill mode temporarily to capture the final value of an animation before canceling it.

    elem.addEventListener('click', async evt => {
      const animation = elem.animate(
        { transform: `translate(${evt.clientX}px, ${evt.clientY}px)` },
        { duration: 800, fill: 'forwards' }
      );
      await animation.finished;
      // commitStyles will record the style up to and including `animation` and
      // update elem’s specified style with the result.
      animation.commitStyles();
      animation.cancel();
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#enumdef-fillmode">Web Animations<br />
<span class="small">The definition of 'fill' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`fill`

52

79

63

No

Yes

No

52

52

63

No

No

6.0

## See also

- [Web Animations API](../web_animations_api)
- [`Element.animate()`](../element/animate) and [`KeyframeEffect.KeyframeEffect()`](../keyframeeffect/keyframeeffect) both accept an object of timing properties including this one.
- The value of this property corresponds to the one in [`EffectTiming`](../effecttiming) as returned by [`getTiming()`](../animationeffect/gettiming) in [`AnimationEffect`](../animationeffect) and [`KeyframeEffect`](../keyframeeffect).
- CSS's `animation-fill-mode`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EffectTiming/fill" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EffectTiming/fill</a>
