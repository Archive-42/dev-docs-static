# Animation()

The `Animation()` constructor of the [Web Animations API](../web_animations_api) returns a new `Animation` object instance.

## Syntax

    var animation = new Animation([effect][, timeline]);

### Parameters

`effect` <span class="badge inline optional">Optional</span>  
The target effect, as an object based on the [`AnimationEffect`](../animationeffect) interface, to assign to the animation. Although in the future other effects such as `SequenceEffect`s or `GroupEffect`s might be possible, the only kind of effect currently available is [`KeyframeEffect`](../keyframeeffect). This can be `null` (which is the default) to indicate that there should be no effect applied.

`timeline` <span class="badge inline optional">Optional</span>  
Specifies the `timeline` with which to associate the animation, as an object of a type based on the [`AnimationTimeline`](../animationtimeline) interface. Currently the only timeline type available is [`DocumentTimeline`](../documenttimeline), but in the future there my be timelines associated with gestures or scrolling, for example. The default value is [`Document.timeline`](../document/timeline), but this can be set to `null` as well.

## Examples

In the [Follow the White Rabbit example](https://codepen.io/rachelnabors/pen/eJyWzm/?editors=0010), the `Animation()` constructor is used to create an `Animation` for the `rabbitDownKeyframes` using the document's `timeline`:

    var rabbitDownAnimation = new Animation(rabbitDownKeyframes, document.timeline);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animation-animation">Web Animations<br />
<span class="small">The definition of 'Animation()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

## See also

- [Web Animations API](../web_animations_api)
- [`Animation`](../animation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Animation/Animation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Animation/Animation</a>
