Web Animations API
==================

The **Web Animations API** allows for synchronizing and timing changes to the presentation of a Web page, i.e. animation of DOM elements. It does so by combining two models: the Timing Model and the Animation Model.

Concepts and usage
------------------

The Web Animations API provides a common language for browsers and developers to describe animations on DOM elements. To get more information on the concepts behind the API and how to use it, read [Using the Web Animations API](web_animations_api/using_the_web_animations_api).

Web Animations interfaces
-------------------------

[`Animation`](animation)  
Provides playback controls and a timeline for an animation node or source. Can take an object created with the [`KeyframeEffect()`](keyframeeffect/keyframeeffect) constructor.

[`KeyframeEffect`](keyframeeffect)  
Describes sets of animatable properties and values, called **keyframes** and their [timing options](effecttiming). These can then be played using the [`Animation()`](animation/animation) constructor.

[`AnimationTimeline`](animationtimeline)  
Represents the timeline of animation. This interface exists to define timeline features (inherited by [`DocumentTimeline`](documenttimeline) and future timeline objects) and is not itself accessed by developers.

[`AnimationEvent`](animationevent)  
Actually part of CSS Animations.

[`DocumentTimeline`](documenttimeline)  
Represents animation timelines, including the default document timeline (accessed using the [`Document.timeline`](document/timeline) property).

[`EffectTiming`](effecttiming)  
[`Element.animate()`](element/animate), [`KeyframeEffectReadOnly.KeyframeEffectReadOnly()`](keyframeeffect/keyframeeffect), and [`KeyframeEffect.KeyframeEffect()`](keyframeeffect/keyframeeffect) all accept an optional dictionary object of timing properties.

Extensions to other interfaces
------------------------------

The Web Animations API adds some new features to [`document`](document) and [`element`](element).

### Extensions to the `Document` interface

[`document.timeline`](document/timeline)  
The `DocumentTimeline` object representing the default document timeline.

[`document.getAnimations()`](document/getanimations)  
Returns an Array of [`Animation`](animation) objects currently in effect on elements in the `document`.

### Extensions to the `Element` interface

[`Element.animate()`](element/animate)  
A shortcut method for creating and playing an animation on an element. It returns the created [`Animation`](animation) object instance.

[`Element.getAnimations()`](element/getanimations)  
Returns an Array of [`Animation`](animation) objects currently affecting an element or which are scheduled to do so in future.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/">Web Animations</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

See also
--------

-   [Using the Web Animations API](web_animations_api/using_the_web_animations_api)
-   [Web Animations demos](https://mozdevs.github.io/Animation-examples/)
-   [Polyfill](https://github.com/web-animations/web-animations-js)
-   Firefox's current implementation: [AreWeAnimatedYet](https://birtles.github.io/areweanimatedyet/)
-   [Browser support test](https://codepen.io/danwilson/pen/xGBKVq)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Animations_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Web_Animations_API</a>
