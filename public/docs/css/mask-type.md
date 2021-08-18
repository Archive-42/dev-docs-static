# mask-type

The `mask-type` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets whether an SVG [`<mask>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/mask) element is used as a _luminance_ or an _alpha_ mask. It applies to the `<mask>` element itself.

    /* Keyword values */
    mask-type: luminance;
    mask-type: alpha;

    /* Global values */
    mask-type: inherit;
    mask-type: initial;
    mask-type: unset;

This property may be overridden by the [`mask-mode`](mask-mode) property, which has the same effect but applies to the element where the mask is used. Alpha masks will generally be faster to render.

## Syntax

The `mask-type` property is specified as one of the keyword values listed below.

### Values

`luminance`  
Is a keyword indicating that the associated mask image is a luminance mask, i.e., that its [relative luminance](https://en.wikipedia.org/wiki/Luminance_%28relative%29) values must be used when applying it.

`alpha`  
Is a keyword indicating that the associated mask image is an alpha mask, i.e., that its [alpha channel](https://en.wikipedia.org/wiki/Alpha_compositing) values must be used when applying it.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>luminance</code></td></tr><tr class="even"><td>Applies to</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/SVG/Element/mask"><code>&lt;mask&gt;</code></a> elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    luminance | alpha

## Examples

### Setting an alpha mask

#### HTML

    <div class="redsquare"></div>
    <svg version="1.1" xmlns="http://www.w3.org/2000/svg"
        xmlns:xlink="http://www.w3.org/1999/xlink" width="0" height="0">
      <defs>
        <mask id="m" maskContentUnits="objectBoundingBox"
          style="mask-type:alpha">
          <rect x=".1" y=".1" width=".8" height=".8"
              fill="red" fill-opacity="0.7"/>
        </mask>
      </defs>
    </svg>

#### CSS

    .redsquare {
      height: 100px;
      width: 100px;
      background-color: rgb(128, 128, 128);
      border: solid 1px black;
      mask: url("#m");
    }

#### Result

### Setting a luminance mask

#### HTML

    <div class="redsquare"></div>
    <svg version="1.1" xmlns="http://www.w3.org/2000/svg"
        xmlns:xlink="http://www.w3.org/1999/xlink" width="0" height="0">
      <defs>
        <mask id="m" maskContentUnits="objectBoundingBox"
          style="mask-type:luminance">
          <rect x=".1" y=".1" width=".8" height=".8"
              fill="red" fill-opacity="0.7"/>
        </mask>
      </defs>
    </svg>

#### CSS

    .redsquare {
      height: 100px;
      width: 100px;
      background-color: rgb(128, 128, 128);
      border: solid 1px black;
      mask: url("#m");
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/css-masking-1/#the-mask-type">CSS Masking Module Level 1<br />
<span class="small">The definition of 'mask-type' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`mask-type`

24

79

35

20-52

No

15

6.1

37

25

35

20-52

14

7

1.5

## See also

- Other mask-related properties: [`mask`](mask), [`mask-mode`](mask-mode)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/mask-type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/mask-type</a>
