Window.onmozbeforepaint
=======================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Note:**This method was removed from Firefox 11 and onward.

### Summary

An event handler for the `MozBeforePaint` event. This is used in concert with the [`window.mozRequestAnimationFrame()`](../window/requestanimationframe) method to perform smooth, synchronized animations from JavaScript code.

### Syntax

    window.onmozbeforepaint = funcRef;

-   `funcRef` is the handler function.

### Example

See [`window.mozRequestAnimationFrame()`](../window/requestanimationframe) for an example.

### Notes

This event fires immediately before the browser window is repainted, if the event has been requested by one or more scripts calling [`window.mozRequestAnimationFrame()`](../window/requestanimationframe). The event handler receives as an input parameter an event whose `timeStamp` property is the time, in milliseconds since epoch, that is the "current time" for the current animation frame. This time is the same for all animations being run in the same browser window, including those using the [`window.mozRequestAnimationFrame()`](../window/requestanimationframe) method, [CSS transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions), and SMIL animations.

### Specifications

Not part of a specification.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/onmozbeforepaint" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/onmozbeforepaint</a>
