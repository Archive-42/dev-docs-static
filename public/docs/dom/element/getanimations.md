# Element.getAnimations()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `getAnimations()` method of the [`Element`](../element) interface (specified on the `Animatable` mixin) returns an array of all [`Animation`](../animation) objects affecting this element or which are scheduled to do so in future. It can optionally return [`Animation`](../animation) objects for descendant elements too.

**Note**: This array includes [CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations), [CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions), and [Web Animations](../web_animations_api).

## Syntax

    const animations = Element.getAnimations(options);

### Parameters

`options Optional`  
An options object containing the following property:

`subtree`  
A boolean value which, if `true`, causes animations that target descendants of _Element_ to be returned as well. This includes animations that target any CSS [pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements) attached to _Element_ or one of its descendants. Defaults to `false`.

### Return value

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`Animation`](../animation) objects, each representing an animation currently targeting the [`Element`](../element) on which this method is called, or one of its descendant elements if `{ subtree: true }` is specified.

## Examples

The following code snippet will wait for all animations on `elem` and its descendants to finish before removing the element from the document.

    Promise.all(
      elem.getAnimations({ subtree: true })
        .map(animation => animation.finished)
    ).then(() => elem.remove());

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animatable-getanimations">Web Animations<br />
<span class="small">The definition of 'Animatable.getAnimations()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`getAnimations`

84

79

67-79

Does not support the `subtree` option.

44-67

Does not automatically flush pending style changes and does not support the `subtree` option.

38-44

Does not automatically flush pending style changes and does not support the `subtree` option.

84

79

75

63-75

No

70

66

54-66

Does not support the `subtree` option.

31-54

Does not automatically flush pending style changes and does not support the `subtree` option.

25-31

Does not automatically flush pending style changes and does not support the `subtree` option.

Yes

Does not support the `subtree` option.

84

84

79

67-79

Does not support the `subtree` option.

44-67

Does not automatically flush pending style changes and does not support the `subtree` option.

38-44

Does not automatically flush pending style changes and does not support the `subtree` option.

79

63-79

60

57

48-57

Does not support the `subtree` option.

32-48

Does not automatically flush pending style changes and does not support the `subtree` option.

25-32

Does not automatically flush pending style changes and does not support the `subtree` option.

Yes

Does not support the `subtree` option.

14.0

## See also

- [Web Animations API](../web_animations_api)
- [CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations)
- [CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions)
- [`Document.getAnimations()`](../document/getanimations) - Fetch all animations in the document
- [`Animation`](../animation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/getAnimations" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/getAnimations</a>
