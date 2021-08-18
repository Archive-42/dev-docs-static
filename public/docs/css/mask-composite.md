# mask-composite

The `mask-composite` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property represents a compositing operation used on the current mask layer with the mask layers below it.

    /* Keyword values */
    mask-composite: add;
    mask-composite: subtract;
    mask-composite: intersect;
    mask-composite: exclude;

    /* Global values */
    mask-composite: inherit;
    mask-composite: initial;
    mask-composite: unset;

## Syntax

One or more of the keyword values listed below, separated by commas.

### Values

For the composition the current mask layer is referred to as _source_, while all layers below it are referred to as _destination_.

`add`  
The source is placed over the destination.

`subtract`  
The source is placed, where it falls outside of the destination.

`intersect`  
The parts of source that overlap the destination, replace the destination.

`exclude`  
The non-overlapping regions of source and destination are combined.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>add</code></td></tr><tr class="even"><td>Applies to</td><td>all elements; In SVG, it applies to container elements excluding the <a href="https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs"><code>defs</code></a> element and all graphics elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <compositing-operator>#where
    <compositing-operator> = add | subtract | intersect | exclude

## Examples

### Compositing mask layers with addition

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/css-masking-1/#the-mask-composite">CSS Masking Module Level 1<br />
<span class="small">The definition of 'mask-composite' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`mask-composite`

No

See also [`-webkit-mask-composite`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-composite) for a similar non-standard property that uses different keywords.

18-79

53

No

No

See also [`-webkit-mask-composite`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-composite) for a similar non-standard property that uses different keywords.

No

See also [`-webkit-mask-composite`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-composite) for a similar non-standard property that uses different keywords.

No

See also [`-webkit-mask-composite`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-composite) for a similar non-standard property that uses different keywords.

No

See also [`-webkit-mask-composite`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-composite) for a similar non-standard property that uses different keywords.

53

No

See also [`-webkit-mask-composite`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-composite) for a similar non-standard property that uses different keywords.

No

See also [`-webkit-mask-composite`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-composite) for a similar non-standard property that uses different keywords.

No

See also [`-webkit-mask-composite`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-composite) for a similar non-standard property that uses different keywords.

## See also

- [Clipping and Masking in CSS](https://css-tricks.com/clipping-masking-css/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/mask-composite" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/mask-composite</a>
