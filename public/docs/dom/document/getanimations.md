# Document.getAnimations()

The `getAnimations()` method of the [`Document`](../document) interface returns an array of all [`Animation`](../animation) objects currently in effect whose target elements are descendants of the document. This array includes [CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations), [CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions), and [Web Animations](../web_animations_api).

## Syntax

    getAnimations();

### Parameters

None.

### Return value

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`Animation`](../animation) objects, each representing one animation currently associated with elements which are descendants of the [`Document`](../document) on which it's called.

## Examples

The following code snippet will slow down all animations on a page by halving their [`Animation.playbackRate`](../animation/playbackrate).

    document.getAnimations().forEach(
      function (animation) {
        animation.playbackRate *= .5;
      }
    );

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-documentorshadowroot-getanimations">Web Animations<br />
<span class="small">The definition of 'DocumentOrShadowRoot.getAnimations()' in that specification.</span></a></td></tr></tbody></table>

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

61

Implements an older version of the specification.

84

79

Implements an older version of the specification.

75

63-75

No

70

48

Implements an older version of the specification.

14

13.1

Implements an older version of the specification, see Webkit bug [179536](https://webkit.org/b/179536).

84

84

61

Implements an older version of the specification.

79

60

45

Implements an older version of the specification.

14

13.4

Implements an older version of the specification, see Webkit bug [179536](https://webkit.org/b/179536).

14.0

## See also

- [Web Animations API](../web_animations_api)
- [CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations)
- [CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions)
- [`Element.getAnimations()`](../element/getanimations) - Fetch only the animations on a single [`Element`](../element) and its descendants.
- [`Animation`](../animation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/getAnimations" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/getAnimations</a>
