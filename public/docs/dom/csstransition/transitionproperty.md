# CSSTransition.transitionProperty

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `transitionProperty` property of the [`CSSTransition`](../csstransition) interface returns the **expanded transition property name** of the transition. This is the longhand CSS property for which the transition was generated.

## Syntax

    const transitionProperty = CSSAnimation.transitionProperty;

### Value

A [`CSSOMString`](../cssomstring).

## Examples

### Returning the transitionProperty

The transition in the following example changes the width of the box on hover. Calling [`Element.getAnimations()`](../element/getanimations) returns an array of all [`Animation`](../animation) objects. In our case this returns a `CSSTransition` object, representing the animation created. The `transitionProperty` property returns the property that the transition is created for, which is `width`.

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
      console.log(animations[0].propertyName);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transitions-2/#dom-csstransition-transitionproperty">CSS Transitions Level 2<br />
<span class="small">The definition of 'transitionProperty' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.CSSAnimation.transitionProperty`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSTransition/transitionProperty" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSTransition/transitionProperty</a>
