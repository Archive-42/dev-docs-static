# scroll-snap-align

The `scroll-snap-align` property specifies the box’s snap position as an alignment of its snap area (as the alignment subject) within its snap container’s snapport (as the alignment container). The two values specify the snapping alignment in the block axis and inline axis, respectively. If only one value is specified, the second value defaults to the same value.

## Syntax

    /* Keyword values */
    scroll-snap-align: none;
    scroll-snap-align: start end; /* when two values set first is block, second inline */
    scroll-snap-align: center;

    /* Global values */
    scroll-snap-align: inherit;
    scroll-snap-align: initial;
    scroll-snap-align: unset;

### Values

`none`  
The box does not define a snap position in that axis.

`start`  
The start alignment of this box's scroll snap area, within the scroll container's snapport is a snap position in this axis.

`end`  
The end alignment of this box's scroll snap area, within the scroll container's snapport is a snap position in this axis.

`center`  
The center alignment of this box's scroll snap area, within the scroll container's snapport is a snap position in this axis.

Safari currently has the two value syntax in the wrong order, the first value being inline the second block. See [bug \#191865](https://bugs.webkit.org/show_bug.cgi?id=191865).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    [ none | start | end | center ]{1,2}

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-scroll-snap-1/#propdef-scroll-snap-align">CSS Scroll Snap Module Level 1<br />
<span class="small">The definition of 'scroll-snap-align' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`scroll-snap-align`

69

79

68

No

56

11

69

69

68

48

11

10.0

## See also

- [CSS Scroll Snap](css_scroll_snap)
- [Well-Controlled Scrolling with CSS Scroll Snap](https://developers.google.com/web/updates/2018/07/css-scroll-snap)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-align" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-align</a>
