# Animation.onremove

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The [`Animation`](../animation) interface's `onremove` property (from the [Web Animations API](../web_animations_api)) is the event handler for the `remove` event. This event is sent when the animation is removed (i.e., put into an `active` replace state).

## Syntax

    var removeHandler = animation.onremove;

    animation.onremove = removeHandler;

### Value

A function to be called to handle the `remove` event, or `null` if no `remove` event handler is set.

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

A console message is logged each time an animation it removed, invoked when the `remove `event is fired.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animation-onremove">Web Animations<br />
<span class="small">The definition of 'Animation.onremove' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`onremove`

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
- [`Animation`](../animation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Animation/onremove" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Animation/onremove</a>
