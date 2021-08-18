# Animation

The `Animation` interface of the [Web Animations API](web_animations_api) represents a single animation player and provides playback controls and a timeline for an animation node or source.

## Constructor

[`Animation()`](animation/animation)  
Creates a new `Animation` object instance.

## Properties

[`Animation.currentTime`](animation/currenttime)  
The current time value of the animation in milliseconds, whether running or paused. If the animation lacks a [`timeline`](animationtimeline), is inactive or hasn't been played yet, its value is `null`.

[`Animation.effect`](animation/effect)  
Gets and sets the [`AnimationEffect`](animationeffect) associated with this animation. This will usually be a [`KeyframeEffect`](keyframeeffect) object.

[`Animation.finished`](animation/finished) <span class="badge inline readonly">Read only </span>  
Returns the current finished Promise for this animation.

[`Animation.id`](animation/id)  
Gets and sets the `String` used to identify the animation.

[`Animation.pending`](animation/pending) <span class="badge inline readonly">Read only </span>  
Indicates whether the animation is currently waiting for an asynchronous operation such as initiating playback or pausing a running animation.

[`Animation.playState`](animation/playstate) <span class="badge inline readonly">Read only </span>  
Returns an enumerated value describing the playback state of an animation.

[`Animation.playbackRate`](animation/playbackrate)  
Gets or sets the playback rate of the animation.

[`Animation.ready`](animation/ready) <span class="badge inline readonly">Read only </span>  
Returns the current ready Promise for this animation.

[`animation.replaceState`](animation/replacestate)  
Returns the replace state of the animation. This will be `active` if the animation has been replaced, or `persisted` if [`Animation.persist()`](animation/persist) has been invoked on it.

[`Animation.startTime`](animation/starttime)  
Gets or sets the scheduled time when an animation's playback should begin.

[`Animation.timeline`](animation/timeline)  
Gets or sets the [`timeline`](animationtimeline) associated with this animation.

### Event handlers

[`Animation.oncancel`](animation/oncancel)  
Gets and sets the event handler for the `cancel` event.

[`Animation.onfinish`](animation/onfinish)  
Gets and sets the event handler for the `finish` event.

[`animation.onremove`](animation/onremove)  
Allows you to set and run an event handler that fires when the animation is removed (i.e., put into an `active` replace state).

## Methods

[`Animation.cancel()`](animation/cancel)  
Clears all [`keyframeEffects`](keyframeeffect) caused by this animation and aborts its playback.

[`animation.commitStyles()`](animation/commitstyles)  
Commits the end styling state of an animation to the element being animated, even after that animation has been removed. It will cause the end styling state to be written to the element being animated, in the form of properties inside a `style` attribute.

[`Animation.finish()`](animation/finish)  
Seeks either end of an animation, depending on whether the animation is playing or reversing.

[`Animation.pause()`](animation/pause)  
Suspends playing of an animation.

[`animation.persist()`](animation/persist)  
Explicitly persists an animation, when it would otherwise be removed due to the browser's [Automatically removing filling animations](#automatically_removing_filling_animations) behavior.

[`Animation.play()`](animation/play)  
Starts or resumes playing of an animation, or begins the animation again if it previously finished.

[`Animation.reverse()`](animation/reverse)  
Reverses playback direction, stopping at the start of the animation. If the animation is finished or unplayed, it will play from end to beginning.

[`Animation.updatePlaybackRate()`](animation/updateplaybackrate)  
Sets the speed of an animation after first synchronizing its playback position.

## Automatically removing filling animations

It is possible to trigger a large number of animations on the same element. If they are indefinite (i.e., forwards-filling), this can result in a huge animations list, which could create a memory leak. For this reason, modern browsers have implemented the part of the Web Animations spec that automatically removes overriding forward filling animations, unless the developer explicitly specifies to keep them.

You can see this in action in our simple [replace indefinite animations demo](https://mdn.github.io/dom-examples/web-animations-api/replace-indefinite-animations.html). The related JavaScript features are:

- [`animation.commitStyles()`](animation/commitstyles) for commiting the end styling state of an animation to the element being animated, even after that animation has been removed.
- [`animation.onremove`](animation/onremove) for setting and running an event handler that fires when the animation is removed (i.e., put into an `active` replace state).
- [`animation.persist()`](animation/persist) for when you explicitly want an animations to be retained.
- [`animation.replaceState`](animation/replacestate) to return the replace state of the animation. This will be `active` if the animation has been removed, or `persisted` if <span class="page-not-created">`persist()`</span> has been invoked.

## Accessibility concerns

Blinking and flashing animation can be problematic for people with cognitive concerns such as Attention Deficit Hyperactivity Disorder (ADHD). Additionally, certain kinds of motion can be a trigger for Vestibular disorders, epilepsy, and migraine, and Scotopic sensitivity.

Consider providing a mechanism for pausing or disabling animation, as well as using the [Reduced Motion Media Query](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion) to create a complimentary experience for users who have expressed a preference for no animated experiences.

- [Designing Safer Web Animation For Motion Sensitivity · An A List Apart Article](https://alistapart.com/article/designing-safer-web-animation-for-motion-sensitivity)
- [An Introduction to the Reduced Motion Media Query | CSS-Tricks](https://css-tricks.com/introduction-reduced-motion-media-query/)
- [Responsive Design for Motion | WebKit](https://webkit.org/blog/7551/responsive-design-for-motion/)
- [MDN Understanding WCAG, Guideline 2.2 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Operable#guideline_2.2_%e2%80%94_enough_time_provide_users_enough_time_to_read_and_use_content)
- [Understanding Success Criterion 2.2.2 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/time-limits-pause.html)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#the-animation-interface">Web Animations<br />
<span class="small">The definition of 'Animation' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`Animation`

44

39-44

79

48

No

26

13.1

44

39-44

44

39-44

48

26

13.4

4.0

`Animation`

61

79

48

No

48

13.1

61

61

48

45

13.4

8.0

`cancel`

39

79

48

No

26

13.1

39

39

48

26

13.4

4.0

`commitStyles`

84

84

75

No

70

13.1

No

84

79

60

13.4

14.0

`currentTime`

39

79

48

No

26

13.1

39

39

48

26

13.4

4.0

`effect`

75

79

63

No

62

13.1

75

75

63

54

13.4

11.0

`finish`

39

79

48

No

26

13.1

39

39

48

26

13.4

4.0

`finished`

84

84

63

No

70

13.1

No

84

63

60

13.4

14.0

`id`

50

79

48

No

37

13.1

50

50

48

37

13.4

5.0

`oncancel`

50

79

48

No

37

13.1

50

50

48

37

13.4

5.0

`onfinish`

39

79

48

No

26

13.1

39

39

48

26

13.4

4.0

`onremove`

84

84

75

No

70

13.1

No

84

79

60

13.4

14.0

`pause`

39

79

48

No

26

13.1

39

39

48

26

13.4

4.0

`pending`

No

No

59

Prior to version 59, the pending status was reported by a `"pending"` value returned from [`Animation.playState`](https://developer.mozilla.org/docs/Web/API/Animation/playState).

No

No

13.1

No

No

59

Prior to version 59, the pending status was reported by a `"pending"` value returned from [`Animation.playState`](https://developer.mozilla.org/docs/Web/API/Animation/playState).

No

13.4

No

`persist`

84

84

75

No

70

13.1

No

84

79

60

13.4

14.0

`play`

39

79

48

No

26

13.1

39

39

48

26

13.4

4.0

`playbackRate`

39

79

48

No

26

13.1

39

39

48

26

13.4

4.0

`playState`

39

Before Chrome 50/Opera 37, this property returned `idle` for an animation that had not yet started. Starting with Chrome 50/Opera 37, it shows `paused`.

79

48

Prior to Firefox 59, this property returned `pending` for Animations with incomplete asynchronous operations but as of Firefox 59 this is indicated by the separate [`Animation.pending`](https://developer.mozilla.org/docs/Web/API/Animation/pending) property. This reflects recent changes to the specification.

No

26

Before Chrome 50/Opera 37, this property returned `idle` for an animation that had not yet started. Starting with Chrome 50/Opera 37, it shows `paused`.

13.1

39

Before Chrome 50/Opera 37, this property returned `idle` for an animation that had not yet started. Starting with Chrome 50/Opera 37, it shows `paused`.

39

Before Chrome 50/Opera 37, this property returned `idle` for an animation that had not yet started. Starting with Chrome 50/Opera 37, it shows `paused`.

48

Prior to Firefox 59, this property returned `pending` for Animations with incomplete asynchronous operations but as of Firefox 59 this is indicated by the separate [`Animation.pending`](https://developer.mozilla.org/docs/Web/API/Animation/pending) property. This reflects recent changes to the specification.

26

Before Chrome 50/Opera 37, this property returned `idle` for an animation that had not yet started. Starting with Chrome 50/Opera 37, it shows `paused`.

13.4

4.0

Before Samsung Internet 5.0/Opera 37, this property returned `idle` for an animation that had not yet started. Starting with Samsung Internet 5.0/Opera 37, it shows `paused`.

`ready`

84

84

63

No

70

13.1

No

84

63

60

13.4

14.0

`remove_filling_animation`

No

Currently Chrome Canary only

No

75

No

No

13.1

No

No

Currently Chrome Canary only

79

No

13.4

No

`replaceState`

84

84

75

No

70

13.1

No

84

79

60

13.4

14.0

`reverse`

39

79

48

No

26

13.1

39

39

48

26

13.4

4.0

`startTime`

39

79

48

No

26

13.1

39

39

48

26

13.4

4.0

`timeline`

84

84

75

Currently only the getter is supported

No

70

13.1

Currently only the getter is supported

No

84

79

Currently only the getter is supported

60

13.4

Currently only the getter is supported

14.0

`updatePlaybackRate`

No

No

60

No

No

13.1

No

No

60

No

13.4

No

## See also

- [Web Animations API](web_animations_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Animation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Animation</a>
