# scroll-padding-bottom

The `scroll-padding-bottom` property defines offsets for the bottom of the optimal viewing region of the scrollport: the region used as the target region for placing things in view of the user. This allows the author to exclude regions of the scrollport that are obscured by other content (such as fixed-positioned toolbars or sidebars) or to put more breathing room between a targeted element and the edges of the scrollport.

## Syntax

    /* Keyword values */
    scroll-padding-bottom: auto;

    /* <length> values */
    scroll-padding-bottom: 10px;
    scroll-padding-bottom: 1em;
    scroll-padding-bottom: 10%;

    /* Global values */
    scroll-padding-bottom: inherit;
    scroll-padding-bottom: initial;
    scroll-padding-bottom: unset;

### Values

`<length-percentage>`  
An inwards offset from the bottom edge of the scrollport, as a valid length or a percentage.

`auto`  
The offset is determined by the user agent. This will generally be 0px, but a user agent is able to detect and do something else if a non-zero value is more appropriate.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>scroll containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>relative to the scroll container's scrollport</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="even"><td>Animation type</td><td>by computed value type</td></tr></tbody></table>

## Formal syntax

    auto | <length-percentage>where
    <length-percentage> = <length> | <percentage>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-scroll-snap-1/#propdef-scroll-padding-bottom">CSS Scroll Snap Module Level 1<br />
<span class="small">The definition of 'scroll-padding-bottom' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`scroll-padding-bottom`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-bottom" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-bottom</a>
