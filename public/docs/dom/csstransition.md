# CSSTransition

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `CSSTransition` interface of the [Web Animations API](web_animations_api) represents an [`Animation`](animation) object used for a [CSS Transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions).

## Properties

Inherits methods from its ancestor [`Animation`](animation) and adds <span class="page-not-created">`transitionProperty`</span>.

[`CSSTransition.transitionProperty`](csstransition/transitionproperty)<span class="badge inline readonly">Read only </span>  
Returns the transition CSS property name as a [`CSSOMString`](cssomstring).

### Event handlers

No specific event handlers; inherits methods from its ancestor [`Animation`](animation).

## Methods

No specific methods; inherits methods from its ancestor [`Animation`](animation).

## Examples

### Inspecting the returned CSSTransition

The transition in the following example changes the width of the box on hover. Calling [`Element.getAnimations()`](element/getanimations) returns an array of all [`Animation`](animation) objects. In our case this returns a `CSSTransition` object, representing the animation created.

    .box {
      background-color: #165baa;
      color: #fff;
      width: 100px;
      height: 100px;
      transition: width 4s;
    }

    .box:hover {
      width: 200px;
    }

    const item = document.querySelector(".box");
    item.addEventListener('transitionrun', () => {
      let animations = document.querySelector(".box").getAnimations();
      console.log(animations[0]);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transitions-2/#the-CSSTransition-interface">CSS Transitions Level 2<br />
<span class="small">The definition of 'CSSTransition' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSTransition`

78

84

75

No

65

13.1

78

78

No

56

13.4

12.0

`transitionProperty`

84

84

75

No

65

13.1

78

78

No

56

13.4

12.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSTransition" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSTransition</a>
