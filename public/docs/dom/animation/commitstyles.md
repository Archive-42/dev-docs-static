# Animation.commitStyles()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `commitStyles()` method of the [Web Animations API](../web_animations_api)'s [`Animation`](../animation) interface commits the end styling state of an animation to the element being animated, even after that animation has been removed. It will cause the end styling state to be written to the element being animated, in the form of properties inside a `style` attribute.

## Syntax

    animation.commitStyles();

### Parameters

None.

### Return value

None.

## Examples

    const divElem = document.querySelector('div');

    document.body.addEventListener('mousemove', evt => {
      let anim = divElem.animate(
        { transform: `translate(${ evt.clientX}px, ${evt.clientY}px)` },
        { duration: 500, fill: 'forwards' }
      );

      anim.commitStyles();
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animation-commitstyles">Web Animations<br />
<span class="small">The definition of 'commitStyles()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`commitStyles`

84

84

75

No

70

13.1

No

84

79

60

13.4

14.0

## See also

- [Web Animations API](../web_animations_api)
- [`Animation`](../animation) for other methods and properties you can use to control web page animation.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Animation/commitStyles" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Animation/commitStyles</a>
