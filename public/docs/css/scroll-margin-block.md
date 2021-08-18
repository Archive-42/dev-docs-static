# scroll-margin-block

The `scroll-margin-block` [shorthand property](shorthand_properties) sets the scroll margins of an element in the block dimension.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`scroll-margin-block-end`](scroll-margin-block-end)
- [`scroll-margin-block-start`](scroll-margin-block-start)

## Syntax

    /* <length> values */
    scroll-margin-block: 10px;
    scroll-margin-block: 1em .5em ;

    /* Global values */
    scroll-margin-block: inherit;
    scroll-margin-block: initial;
    scroll-margin-block: unset;

### Values

`<length>`  
An outset from the corresponding edge of the scroll container.

## Description

The scroll-margin values represent outsets defining the scroll snap area that is used for snapping this box to the snapport. The scroll snap area is determined by taking the transformed border box, finding its rectangular bounding box (axis-aligned in the scroll container’s coordinate space), then adding the specified outsets.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>by computed value type</td></tr></tbody></table>

## Formal syntax

    <length>{1,2}

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-scroll-snap-1/#propdef-scroll-margin-block">CSS Scroll Snap Module Level 1<br />
<span class="small">The definition of 'scroll-margin-block' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`scroll-margin-block`

69

79

68

No

56

14.1

69

69

68

48

14.5

10.0

## See also

- [CSS Scroll Snap](css_scroll_snap)
- [Well-Controlled Scrolling with CSS Scroll Snap](https://developers.google.com/web/updates/2018/07/css-scroll-snap)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-block" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-block</a>
