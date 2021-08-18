# CSSAnimation

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `animationName` property of the [`CSSAnimation`](../cssanimation) interface returns the [`animation-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name). This specifies one or more keyframe at-rules which describe the animation applied to the element.

## Syntax

    const animationName = CSSAnimation.animationName;

### Value

A [`CSSOMString`](../cssomstring).

## Examples

### Returning the animationName

The animation in the following example is defined in CSS with the name `slide-in`. Calling [`Element.getAnimations()`](../element/getanimations) returns an array of all [`Animation`](../animation) objects. The `animationName` property returns the name given to the animation, in our case `slide-in`.

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
    console.log(animations[0].animationName);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-2/#dom-cssanimation-animationname">CSS Animations Level 2<br />
<span class="small">The definition of 'animationName' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSAnimation/animationName" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSAnimation/animationName</a>
