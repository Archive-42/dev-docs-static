# scroll-padding

The `scroll-padding` [shorthand property](shorthand_properties) sets scroll padding on all sides of an element at once, much like the [`padding`](padding) property does for padding on an element.

The `scroll-padding-*` properties define offsets for the optimal viewing region of the scrollport: the region used as the target region for placing things in view of the user. This allows the author to exclude regions of the scrollport that are obscured by other content (such as fixed-positioned toolbars or sidebars), or to put more breathing room between a targeted element and the edges of the scrollport.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`scroll-padding-bottom`](scroll-padding-bottom)
- [`scroll-padding-left`](scroll-padding-left)
- [`scroll-padding-right`](scroll-padding-right)
- [`scroll-padding-top`](scroll-padding-top)

## Syntax

    /* Keyword values */
    scroll-padding: auto;

    /* <length> values */
    scroll-padding: 10px;
    scroll-padding: 1em .5em 1em 1em;
    scroll-padding: 10%;

    /* Global values */
    scroll-padding: inherit;
    scroll-padding: initial;
    scroll-padding: unset;

### Values

[`<length-percentage>`](length-percentage)  
An inwards offset from the corresponding edge of the scrollport, as a valid [`<length>`](length) or a [`<percentage>`](percentage).

`auto`  
The offset is determined by the user agent. This will generally be `0px`, but the user agent is free to detect and do something else if a non-zero value is more appropriate.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>scroll containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>relative to the scroll container's scrollport</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="even"><td>Animation type</td><td>by computed value type</td></tr></tbody></table>

## Formal syntax

    [ auto | <length-percentage> ]{1,4}where
    <length-percentage> = <length> | <percentage>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-scroll-snap-1/#propdef-scroll-padding">CSS Scroll Snap Module Level 1<br />
<span class="small">The definition of 'scroll-padding' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`scroll-padding`

69

79

68

No

56

11

Scroll padding is not applied for scrolls to fragment target or `scrollIntoView()`, see [bug 179379](https://webkit.org/b/179379).

69

69

68

48

11

Scroll padding is not applied for scrolls to fragment target or `scrollIntoView()`, see [bug 179379](https://webkit.org/b/179379).

10.0

## See also

- [CSS Scroll Snap](css_scroll_snap)
- [Well-Controlled Scrolling with CSS Scroll Snap](https://developers.google.com/web/updates/2018/07/css-scroll-snap)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding</a>
