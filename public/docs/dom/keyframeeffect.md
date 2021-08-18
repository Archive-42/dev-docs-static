KeyframeEffect
==============

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `KeyframeEffect` interface of the [Web Animations API](web_animations_api) lets us create sets of animatable properties and values, called **keyframes.** These can then be played using the [`Animation()`](animation/animation) constructor.

Constructor
-----------

[`KeyframeEffect()`](keyframeeffect/keyframeeffect)  
Returns a new `KeyframeEffect` object instance, and also allows you to clone an existing keyframe effect object instance.

Properties
----------

[`KeyframeEffect.target`](keyframeeffect/target)  
Gets and sets the element, or originating element of the pseudo-element, being animated by this object. This may be `null` for animations that do not target a specific element or pseudo-element.

 <span class="page-not-created">`KeyframeEffect.pseudoElement`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Gets and sets the selector of the pseudo-element being animated by this object. This may be `null` for animations that do not target a pseudo-element.

[`KeyframeEffect.iterationComposite`](keyframeeffect/iterationcomposite)  
Gets and sets the iteration composite operation for resolving the property value changes of this keyframe effect.

[`KeyframeEffect.composite`](keyframeeffect/composite)  
Gets and sets the composite operation property for resolving the property value changes between this and other keyframe effects.

Methods
-------

*This interface inherits some of its methods from its parent, [`AnimationEffect`](animationeffect).*

[`AnimationEffect.getComputedTiming()`](animationeffect/getcomputedtiming)  
Returns the calculated, current timing values for this keyframe effect.

[`KeyframeEffect.getKeyframes()`](keyframeeffect/getkeyframes)  
Returns the computed keyframes that make up this effect along with their computed keyframe offsets.

[`AnimationEffect.getTiming()`](animationeffect/gettiming)  
The [`EffectTiming`](effecttiming) object associated with the animation containing all the animation's timing values.

[`KeyframeEffect.setKeyframes()`](keyframeeffect/setkeyframes)  
Replaces the set of keyframes that make up this effect.

[`AnimationEffect.updateTiming()`](animationeffect/updatetiming)  
Updates the specified timing properties.

Examples
--------

In the [Follow the White Rabbit example](https://codepen.io/rachelnabors/pen/eJyWzm/?editors=0010), the KeyframeEffect constructor is used to create a set of keyframes that dictate how the White Rabbit should animate down the hole:

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#the-keyframeeffect-interface">Web Animations<br />
<span class="small">The definition of 'KeyframeEffect' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`composite`

84

?

80

63-79

No

71

No

84

84

80

63-79

60

No

14.0

`getKeyframes`

84

?

63

No

71

No

84

84

63

60

No

14.0

`iterationComposite`

No

?

80

63-79

No

No

No

No

No

80

63-79

No

No

No

`pseudoElement`

84

81

81

75

No

71

68

No

84

84

81

79

60

No

14.0

`setKeyframes`

84

No

63

No

71

No

84

84

63

60

No

14.0

`target`

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

-   [Web Animations API](web_animations_api)
-   [`Animation`](animation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyframeEffect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyframeEffect</a>
