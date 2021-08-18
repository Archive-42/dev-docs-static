ShadowRoot.getAnimations()
==========================

The `getAnimations()` method of the [`ShadowRoot`](../shadowroot) interface returns an array of all [`Animation`](../animation) objects currently in effect whose target elements are descendants of the shadow tree. This array includes [CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations), [CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions), and [Web Animations](../web_animations_api).

Syntax
------

    getAnimations();

### Parameters

None.

### Return value

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`Animation`](../animation) objects, each representing one animation currently associated with elements which are descendants of the [`ShadowRoot`](../shadowroot) on which it's called.

Examples
--------

The following code snippet will slow down all animations in a shadow tree by halving their [`Animation.playbackRate`](../animation/playbackrate).

    let customElem = document.querySelector('my-shadow-dom-element');
    let shadow = customElem.shadowRoot;
    shadow.getAnimations().forEach(
      function (animation) {
        animation.playbackRate *= .5;
      }
    );

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-documentorshadowroot-getanimations">Web Animations<br />
<span class="small">The definition of 'DocumentOrShadowRoot.getAnimations()' in that specification.</span></a></td></tr></tbody></table>

Browser compatibility
---------------------

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

83

84

83

75

72-75

No

70

69

14

84

84

83

79

60

14

14.0

See also
--------

-   [Web Animations API](../web_animations_api)
-   [CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations)
-   [CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions)
-   [`Element.getAnimations()`](../element/getanimations) - Fetch only the animations on a single [`Element`](../element) and its descendants.
-   [`Animation`](../animation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot/getAnimations" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot/getAnimations</a>
