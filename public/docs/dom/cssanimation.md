# CSSAnimation

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `CSSAnimation` interface of the [Web Animations API](web_animations_api) represents an [`Animation`](animation) object.

## Properties

Inherits methods from its ancestor [`Animation`](animation) and adds <span class="page-not-created">`animationName`</span>.

[`CSSAnimation.animationName`](cssanimation/animationname)<span class="badge inline readonly">Read only </span>  
Returns the animation name as a [`CSSOMString`](cssomstring).

### Event handlers

No specific event handlers; inherits methods from its ancestor [`Animation`](animation).

## Methods

No specific methods; inherits methods from its ancestor [`Animation`](animation).

## Examples

### Inspecting the returned CSSAnimation

The animation in the following example is defined in CSS with the name `slide-in`. Calling [`Element.getAnimations()`](element/getanimations) returns an array of all [`Animation`](animation) objects. In our case this returns a `CSSAnimation` object, representing the animation created in CSS.

    .animate {
      animation: slide-in 0.7s both;
    }

    @keyframes slide-in {
      0% {
        transform: translateY(-1000px);
      }
      100% {
        transform: translateY(0);
      }
    }

    let animations = document.querySelector(".animate").getAnimations();
    console.log(animations[0]);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-2/#the-CSSAnimation-interface">CSS Animations Level 2<br />
<span class="small">The definition of 'CSSAnimation' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSAnimation`

84

84

75

No

70

13.1

84

84

79

60

13.4

14.0

`animationName`

84

84

75

No

70

13.1

84

84

79

60

13.4

14.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSAnimation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSAnimation</a>
