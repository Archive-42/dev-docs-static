# scroll-snap-type-y

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `scroll-snap-type-y` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines how strictly snap points are enforced on the vertical axis of the scroll container in case there is one.

Specifying any precise animations or physics used to enforce those snap points is not covered by this property but instead left up to the user agent.

    /* Keyword values */
    scroll-snap-type-y: none;
    scroll-snap-type-y: mandatory;
    scroll-snap-type-y: proximity;

    /* Global values */
    scroll-snap-type-y: inherit;
    scroll-snap-type-y: initial;
    scroll-snap-type-y: unset;

## Syntax

### Values

`none`  
When the visual [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport) of this scroll container is scrolled vertically, it must ignore snap points.

`mandatory`  
The visual viewport of this scroll container will rest on a snap point if it isn't currently scrolled vertically. That means it snaps on that point when the scroll action finished, if possible. If content is added, moved, deleted or resized the scroll offset will be adjusted to maintain the resting on that snap point.

`proximity`  
The visual viewport of this scroll container may come to rest on a snap point if it isn't currently scrolled vertically considering the user agent's scroll parameters. If content is added, moved, deleted or resized the scroll offset may be adjusted to maintain the resting on that snap point.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>scroll containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    none | mandatory | proximity

## Specifications

Not part of any standard.

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

`scroll-snap-type-y`

No

No

39-68

No

No

No

No

No

39-68

No

No

No

## See also

- [`scroll-snap-type-x`](scroll-snap-type-x)
- [`scroll-snap-type`](scroll-snap-type)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-type-y" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-type-y</a>
