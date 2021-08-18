# AnimationPlaybackEvent.AnimationPlaybackEvent()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `AnimationPlaybackEvent()` constructor of the [Web Animations API](../web_animations_api) returns a new `AnimationPlaybackEvent` object instance.

## Syntax

    var animationPlaybackEvent = new AnimationPlaybackEvent(type, eventInitDict);

### Parameters

`type`  
A [`DOMString`](../domstring) representing the name of the event.

`eventInitDict `<span class="badge inline optional">Optional</span>  
An optional `EventInit` dictionary object containing the following fields:

`bubbles` <span class="badge inline optional">Optional</span>  
Defaults to `false`, of type [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), indicating if the event bubbles or not.

`cancelable` <span class="badge inline optional">Optional</span>  
Defaults to `false`, of type [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), indicating if the event can be canceled or not.

`detail` <span class="badge inline optional">Optional</span>  
Defaults to `null`, of type any — an event-dependent value associated with the event.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animationplaybackevent-animationplaybackevent">Web Animations<br />
<span class="small">The definition of 'AnimationPlaybackEvent()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`AnimationPlaybackEvent`

84

84

42

No

70

No

No

84

42

60

No

14.0

## See also

- [Web Animations API](../web_animations_api)
- [`AnimationPlayBackEvent`](../animationplaybackevent)
- [`Animation.playState`](../animation/playstate)
- [`CustomEvent.CustomEvent`](../customevent/customevent)
- [`Event.Event`](../event/event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AnimationPlaybackEvent/AnimationPlaybackEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AnimationPlaybackEvent/AnimationPlaybackEvent</a>
