# Animation.playState

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The ` Animation``.playState ` property of the [Web Animations API](../web_animations_api) returns and sets an enumerated value describing the playback state of an animation.

This property is read-only for CSS Animations and Transitions.

## Syntax

    var currentPlayState = Animation.playState;

    Animation.playState = newState;

### Value

`idle`  
The current time of the animation is unresolved and there are no pending tasks.

`running`  
The animation is running.

`paused`  
The animation was suspended and the [`Animation.currentTime`](currenttime) property is not updating.

`finished`  
The animation has reached one of its boundaries and the [`Animation.currentTime`](currenttime) property is not updating.

Previously, Web Animations defined a `pending` value to indicate that some asynchronous operation such as initiating playback was yet to complete. This is now indicated by the separate [`Animation.pending`](pending) property.

## Example

In the [Growing/Shrinking Alice Game](https://codepen.io/rachelnabors/pen/PNYGZQ?editors=0010) example, players can get an ending with [Alice crying into a pool of tears](https://codepen.io/rachelnabors/pen/EPJdJx?editors=0010). In the game, for performance reasons, the tears should only be animating when they're visible. So they must be paused as soon as they are animated like so:

    // Setting up the tear animations

    tears.forEach(function(el) {
      el.animate(
        tearsFalling,
        {
          delay: getRandomMsRange(-1000, 1000), // randomized for each tear
          duration: getRandomMsRange(2000, 6000), // randomized for each tear
          iterations: Infinity,
          easing: 'cubic-bezier(0.6, 0.04, 0.98, 0.335)'
        });
      el.pause();
    });

    // Play the tears falling when the ending needs to be shown.

    tears.forEach(function(el) {
      el.play();
    });

    // Reset the crying tears animations and pause them.

    tears.forEach(function(el) {
      el.pause();
      el.currentTime = 0;
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#play-state">Web Animations<br />
<span class="small">The definition of 'playState' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- [Web Animations API](../web_animations_api)
- [`Animation`](../animation) for other methods and properties you can use to control web page animation.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Animation/playState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Animation/playState</a>
