# border-top-width

The `border-top-width` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the width of the top border of an element.

## Syntax

    /* Keyword values */
    border-top-width: thin;
    border-top-width: medium;
    border-top-width: thick;

    /* <length> values */
    border-top-width: 10em;
    border-top-width: 3vmax;
    border-top-width: 6px;

    /* Global keywords */
    border-top-width: inherit;
    border-top-width: initial;
    border-top-width: unset;

### Values

`<line-width>`  
Defines the width of the border, either as an explicit nonnegative [`<length>`](length) or a keyword. If it's a keyword, it must be one of the following values:

<table><tbody><tr class="odd"><td><code>thin</code></td><td></td><td>A thin border</td></tr><tr class="even"><td><code>medium</code></td><td></td><td>A medium border</td></tr><tr class="odd"><td><code>thick</code></td><td></td><td>A thick border</td></tr></tbody></table>

**Note:** Because the specification doesn't define the exact thickness denoted by each keyword, the precise result when using one of them is implementation-specific. Nevertheless, they always follow the pattern `thin ≤ medium ≤ thick`, and the values are constant within a single document.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>medium</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>the absolute length or <code>0</code> if <a href="border-top-style"><code>border-top-style</code></a> is <code>none</code> or <code>hidden</code></td></tr><tr class="odd"><td>Animation type</td><td>a <a href="length#interpolation">length</a></td></tr></tbody></table>

## Formal syntax

    <line-width>where
    <line-width> = <length> | thin | medium | thick

## Examples

### HTML

    <div>Element 1</div>
    <div>Element 2</div>

### CSS

    div {
      border: 1px solid red;
      margin: 1em 0;
    }

    div:nth-child(1) {
      border-top-width: thick;
    }
    div:nth-child(2) {
      border-top-width: 2em;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#the-border-width">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'border-top-width' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No significant change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/box.html#border-width-properties">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'border-top-width' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No significant change.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#border-left-width">CSS Level 1<br />
<span class="small">The definition of 'border-top-width' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`border-top-width`

1

12

1

4

3.5

1

2.3

18

4

10.1

1

1.0

## See also

- The other border-width-related CSS properties: [`border-left-width`](border-left-width), [`border-right-width`](border-right-width), [`border-bottom-width`](border-bottom-width), and [`border-width`](border-width).
- The other border-top-related CSS properties: [`border`](border), [`border-top`](border-top), [`border-top-style`](border-top-style), and [`border-top-color`](border-top-color).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-width" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-width</a>
