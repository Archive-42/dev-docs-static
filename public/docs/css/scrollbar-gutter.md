# scrollbar-gutter

The `scrollbar-gutter` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property allows authors to reserve space for the scrollbar, preventing unwanted layout changes as the content grows while also avoiding unnecessary visuals when scrolling isn't needed.

An element's _scrollbar gutter_ is the space between the inner border edge and the outer padding edge, where the browser may display a scrollbar. If no scrollbar is present, the gutter will be painted as an extension of the padding.

The browser determines whether _classic_ scrollbars or _overlay_ scrollbars are used:

- Classic scrollbars are always placed in a gutter, consuming space when present.
- Overlay scrollbars are placed over the content, not in a gutter, and are usually partially transparent.

## Syntax

    /* Initial value */
    scrollbar-gutter: auto;

    /* "stable" keyword, with optional modifiers */
    scrollbar-gutter: stable;
    scrollbar-gutter: stable both;
    scrollbar-gutter: stable force;
    scrollbar-gutter: stable both force;

    /* "always" keyword, with optional modifiers */
    scrollbar-gutter: always;
    scrollbar-gutter: always both;
    scrollbar-gutter: always force;
    scrollbar-gutter: always both force;

### Values

`auto`  
The initial value. Classic scrollbars create a gutter when `overflow` is `scroll`, or when `overflow` is `auto` and the box is overflowing. Overlay scrollbars do not consume space.

`stable`  
When using classic scrollbars, the gutter will be present if `overflow` is `scroll` or `auto` even if the box is not overflowing. When using overlay scrollbars, the gutter will not be present.

`always`  
The scrollbar gutter will always be present when `overflow` is `scroll` or `auto`, regardless of the type of scrollbar or of whether the box is overflowing.

`both`  
If a gutter would be present on one of the inline start/end edges of the box, another will be present on the opposite edge as well.

`force`  
The keywords `stable` and `always` will also be in effect when `overflow` is `visible`, `hidden` or `clip`. Only the gutter will be displayed, not a scrollbar.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | [ stable | always ] && both? && force?

## Examples

### Example 1

Prevent layout changes when the content grows or shrinks:

    .container {
        scrollbar-gutter: stable;
    }

### Example 2

Prevent an overlay scrollbar from obscuring content:

    .container {
        scrollbar-gutter: always;
    }

### Example 3

Keep the symmetry between both sides of the box:

    .container {
        scrollbar-gutter: stable both;
    }

### Example 4

Reserve the same amount of space on the edges of an element that is adjacent to a scrolling element as is being reserved in the latter, so that both line up visually:

    .header {
        scrollbar-gutter: always force;
    }

    .container {
        scrollbar-gutter: always;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-overflow-4/#scrollbar-gutter-property">CSS Overflow Module Level 4<br />
<span class="small">The definition of 'scrollbar-gutter' in that specification.</span></a></td><td><span class="spec-">Unknown</span></td><td>Initial definition.</td></tr></tbody></table>

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

`scrollbar-gutter`

88

No

No

No

No

No

No

88

No

No

No

No

## See also

- [`scrollbar-width`](scrollbar-width)
- [`overflow`](overflow)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scrollbar-gutter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/scrollbar-gutter</a>
