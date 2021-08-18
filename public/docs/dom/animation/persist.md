# Animation.persist()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `persist()` method of the [Web Animations API](../web_animations_api)'s [`Animation`](../animation) interface explicitly persists an animation, when it would otherwise be removed due to the browser's [Automatically removing filling animations](../animation#automatically_removing_filling_animations) behavior.

## Syntax

    animation.persist();

### Parameters

None.

### Return value

None.

## Examples

In our simple [replace indefinite animations demo](https://mdn.github.io/dom-examples/web-animations-api/replace-indefinite-animations.html), you can see the following code:

    const divElem = document.querySelector('div');

    document.body.addEventListener('mousemove', evt => {
      let anim = divElem.animate(
        { transform: `translate(${ evt.clientX}px, ${evt.clientY}px)` },
        { duration: 500, fill: 'forwards' }
      );

      anim.commitStyles();

      //anim.persist()

      anim.onremove = function() {
        console.log('Animation removed');
      }

      console.log(anim.replaceState);
    });

Here we have a `<div>` element, and an event listener that fires the event handler code whenever the mouse moves. The event handler sets up an animation that animates the &lt;div&gt; element to the position of the mouse pointer. This could result in a huge animations list, which could create a memory leak. For this reason, modern browsers automatically remove overriding forward filling animations.

You can see the `replaceState` of the animation being logged at the end of the handler. This will be `active` for each animation by default, or `persisted` if the `persist()` call is uncommented.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animation-persist">Web Animations<br />
<span class="small">The definition of 'persist()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`persist`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Animation/persist" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Animation/persist</a>
