# Element.animate()

The [`Element`](../element) interface's `animate()` method is a shortcut method which creates a new [`Animation`](../animation), applies it to the element, then plays the animation. It returns the created [`Animation`](../animation) object instance.

Elements can have multiple animations applied to them. You can get a list of the animations that affect an element by calling [`Element.getAnimations()`](getanimations).

## Syntax

    var animation = element.animate(keyframes, options);

### Parameters

`keyframes`  
Either an array of keyframe objects, **or** a keyframe object whose property are arrays of values to iterate over. See [Keyframe Formats](../web_animations_api/keyframe_formats) for more details.

`options`  
Either an **integer representing the animation's duration** (in milliseconds), **or** an Object containing one or more timing properties:

`id Optional`  
A property unique to `animate()`: a [`DOMString`](../domstring) with which to reference the animation.

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

You can also include a composite operation or iteration composite operation in your options list:

`composite Optional`  
Determines how values are combined between this animation and other, separate animations that do not specify their own specific composite operation. Defaults to `replace`.

- `add` dictates an additive effect, where each successive iteration builds on the last. For instance with `transform`, a `translateX(-200px)` would not override an earlier `rotate(20deg)` value but result in `translateX(-200px) rotate(20deg)`.
- `accumulate` is similar but a little smarter: `blur(2)` and `blur(5)` become `blur(7)`, not `blur(2) blur(5)`.
- `replace` overwrites the previous value with the new one.

`iterationComposite Optional`  
Determines how values build from iteration to iteration in this animation. Can be set to `accumulate` or `replace` (see above). Defaults to `replace`.

### Return value

Returns an [`Animation`](../animation).

## Examples

In the demo [Down the Rabbit Hole (with the Web Animation API)](https://codepen.io/rachelnabors/pen/rxpmJL/?editors=0010), we use the convenient `animate()` method to immediately create and play an animation on the `#tunnel` element to make it flow upwards, infinitely. Notice the array of objects passed as keyframes and also the timing options block.

    document.getElementById("tunnel").animate([
      // keyframes
      { transform: 'translateY(0px)' },
      { transform: 'translateY(-300px)' }
    ], {
      // timing options
      duration: 1000,
      iterations: Infinity
    });

### Implicit to/from keyframes

In newer browser versions, you are able to set a beginning or end state for an animation only (i.e. a single keyframe), and the browser will infer the other end of the animation if it is able to. For example, consider [this simple animation](https://mdn.github.io/dom-examples/web-animations-api/implicit-keyframes.html) ??? the Keyframe object looks like so:

    let rotate360 = [
      { transform: 'rotate(360deg)' }
    ];

We have only specified the end state of the animation, and the beginning state is implied.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-2/#dom-keyframeeffect-iterationcomposite">Web Animations Level 2<br />
<span class="small">The definition of 'KeyframeAnimationOptions.iterationComposite' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Added the <code>iterationComposite</code> option.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/web-animations-1/#animatable">Web Animations<br />
<span class="small">The definition of 'animate()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`animate`

36

79

48

No

23

13.1

Yes

37

36

48

24

13.4

3.0

`composite_option`

79

79

80

63-79

No

66

No

No

79

63-79

No

No

No

`id_option`

50

79

48

No

37

No

50

50

48

37

No

5.0

`implicit_tofrom`

No

Currently Chrome Canary only

No

75

No

No

13.1

Implementation seems somewhat buggy. More information will follow when available.

No

No

Currently Chrome Canary only

No

No

13.4

Implementation seems somewhat buggy. More information will follow when available.

No

`iterationcomposite_option`

No

No

80

63-79

No

No

No

No

No

63-79

No

No

No

`pseudoElement_option`

81

A valid animation object is returned but the targeted pseudoelement is not visually animated.

81

A valid animation object is returned but the targeted pseudoelement is not visually animated.

75

No

68

A valid animation object is returned but the targeted pseudoelement is not visually animated.

No

No

81

A valid animation object is returned but the targeted pseudoelement is not visually animated.

No

No

No

No

## See also

- [Web Animations API](../web_animations_api)
- [`Element.getAnimations()`](getanimations)
- [`Animation`](../animation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/animate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/animate</a>
