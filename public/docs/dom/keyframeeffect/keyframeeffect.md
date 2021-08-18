KeyframeEffect.KeyframeEffect()
===============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `KeyframeEffect()` constructor of the [Web Animations API](../web_animations_api) returns a new `KeyframeEffect` object instance, and also allows you to clone an existing keyframe effect object instance.

Syntax
------

    var keyframes = new KeyframeEffect(element, keyframeSet, keyframeOptions);
    var keyframes = new KeyframeEffect(sourceKeyFrames);

### Parameters

The first type of constructor (see above) creates a completely new [`KeyframeEffect`](../keyframeeffect) object instance. Its parameters are:

element  
The DOM element to be animated, or `null`.

keyframeSet  
An [keyframe object](../web_animations_api/keyframe_formats) or `null`.

keyframeOptions <span class="badge inline optional">Optional</span>   
Either an integer representing the animation's duration (in milliseconds), or an [`Object`](../effecttiming) containing one or more of the following:  

 [`delay`](../effecttiming/delay) <span class="badge inline optional">Optional</span>   
The number of milliseconds to delay the start of the animation. Defaults to 0.

 [`direction`](../effecttiming/direction) <span class="badge inline optional">Optional</span>   
Whether the animation runs forwards (`normal`), backwards (`reverse`), switches direction after each iteration (`alternate`), or runs backwards and switches direction after each iteration (`alternate-reverse`). Defaults to `"normal"`.

 [`duration`](../effecttiming/duration) <span class="badge inline optional">Optional</span>   
The number of milliseconds each iteration of the animation takes to complete. Defaults to 0. Although this is technically optional, keep in mind that your animation will not run if this value is 0.

 [`easing`](../effecttiming/easing) <span class="badge inline optional">Optional</span>   
The rate of the animation's change over time. Accepts the pre-defined values `"linear"`, `"ease"`, `"ease-in"`, `"ease-out"`, and `"ease-in-out"`, or a custom `"cubic-bezier"` value like `"cubic-bezier(0.42, 0, 0.58, 1)"`. Defaults to `"linear"`.

 [`endDelay`](../effecttiming/enddelay) <span class="badge inline optional">Optional</span>   
The number of milliseconds to delay after the end of an animation. This is primarily of use when sequencing animations based on the end time of another animation. Defaults to 0.

 [`fill`](../effecttiming/fill) <span class="badge inline optional">Optional</span>   
Dictates whether the animation's effects should be reflected by the element(s) prior to playing (`"backwards"`), retained after the animation has completed playing (`"forwards"`), or `both`. Defaults to `"none"`.

 [`iterationStart`](../effecttiming/iterationstart) <span class="badge inline optional">Optional</span>   
Describes at what point in the iteration the animation should start. 0.5 would indicate starting halfway through the first iteration for example, and with this value set, an animation with 2 iterations would end halfway through a third iteration. Defaults to 0.0.

 [`iterations`](../effecttiming/iterations) <span class="badge inline optional">Optional</span>   
The number of times the animation should repeat. Defaults to `1`, and can also take a value of [`Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity) to make it repeat for as long as the element exists.

[`composite`](composite)  
Determines how values are combined between this animation and the element's underlying values.

[`iterationComposite`](iterationcomposite)  
Determines how values build from iteration to iteration in the current animation.

The second type of constructor (see above) creates a clone of an existing [`KeyframeEffect`](../keyframeeffect) object instance. Its parameter is as follows:

sourceKeyFrames  
A [`KeyframeEffect`](../keyframeeffect) object that you want to clone.

Examples
--------

In the [Follow the White Rabbit example](https://codepen.io/rachelnabors/pen/eJyWzm/?editors=0010), the `KeyframeEffect` constructor is used to create a set of keyframes that dictate how the White Rabbit should animate down the hole:

     var rabbitDownKeyframes = new KeyframeEffect(
        whiteRabbit, // element to animate
        [
          { transform: 'translateY(0%)' }, // keyframe
          { transform: 'translateY(100%)' } // keyframe
        ],
        { duration: 3000, fill: 'forwards' } // keyframe options
      );

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-2/#dom-keyframeeffect-iterationcomposite">Web Animations Level 2<br />
<span class="small">The definition of 'KeyframeEffectOptions.iterationComposite' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Added the <code>iterationComposite</code> option.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-keyframeeffect-keyframeeffect">Web Animations<br />
<span class="small">The definition of 'keyframeEffect()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`KeyframeEffect`

75

79

63

No

62

No

75

75

63

54

No

11.0

See also
--------

-   [KeyframeEffect Interface](../keyframeeffect)
-   [Web Animations API](../web_animations_api)
-   [`Animation`](../animation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyframeEffect/KeyframeEffect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyframeEffect/KeyframeEffect</a>
