# transform-origin

The `transform-origin` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the origin for an element's transformations.

The transformation origin is the point around which a transformation is applied. For example, the transformation origin of the `rotate()` function is the center of rotation.

This property is applied by first translating the element by the value of the property, then applying the element's transform, then translating by the negated property value.  
This means, this definition

    transform-origin: -100% 50%;
    transform: rotate(45deg);

results in the same transformation as

    transform-origin: 0 0;
    transform: translate(-100%, 50%) rotate(45deg) translate(100%, -50%);

By default, the origin of a transform is `center`.

## Syntax

    /* One-value syntax */
    transform-origin: 2px;
    transform-origin: bottom;

    /* x-offset | y-offset */
    transform-origin: 3cm 2px;

    /* x-offset-keyword | y-offset */
    transform-origin: left 2px;

    /* x-offset-keyword | y-offset-keyword */
    transform-origin: right top;

    /* y-offset-keyword | x-offset-keyword */
    transform-origin: top right;

    /* x-offset | y-offset | z-offset */
    transform-origin: 2px 30% 10px;

    /* x-offset-keyword | y-offset | z-offset */
    transform-origin: left 5px -3px;

    /* x-offset-keyword | y-offset-keyword | z-offset */
    transform-origin: right bottom 2cm;

    /* y-offset-keyword | x-offset-keyword | z-offset */
    transform-origin: bottom right 2cm;

    /* Global values */
    transform-origin: inherit;
    transform-origin: initial;
    transform-origin: unset;

The `transform-origin` property may be specified using one, two, or three values, where each value represents an offset. Offsets that are not explicitly defined are reset to their corresponding [initial values](initial_value).

If a single [`<length>`](length) or [`<percentage>`](percentage) value is defined, it represents the horizontal offset.

If two or more values are defined and either no value is a keyword, or the only used keyword is `center`, then the first value represents the horizontal offset and the second represents the vertical offset.

- One-value syntax:
  - The value must be a [`<length>`](length), a [`<percentage>`](percentage), or one of the keywords `left`, `center`, `right`, `top`, and `bottom`.
- Two-value syntax:
  - One value must be a [`<length>`](length), a [`<percentage>`](percentage), or one of the keywords `left`, `center`, and `right`.
  - The other value must be a [`<length>`](length), a [`<percentage>`](percentage), or one of the keywords `top`, `center`, and `bottom`.
- Three-value syntax:
  - The first two values are the same as for the two-value syntax.
  - The third value must be a [`<length>`](length). It always represents the Z offset.

### Values

x-offset  
Is a [`<length>`](length) or a [`<percentage>`](percentage) describing how far from the left edge of the box the origin of the transform is set.

offset-keyword  
Is one of the `left`, `right`, `top`, `bottom`, or `center` keyword describing the corresponding offset.

y-offset  
Is a [`<length>`](length) or a [`<percentage>`](percentage) describing how far from the top edge of the box the origin of the transform is set.

x-offset-keyword  
Is one of the `left`, `right`, or `center` keyword describing how far from the left edge of the box the origin of the transform is set.

y-offset-keyword  
Is one of the `top`, `bottom`, or `center` keyword describing how far from the top edge of the box the origin of the transform is set.

z-offset  
Is a [`<length>`](length) (and never a [`<percentage>`](percentage) which would make the statement invalid) describing how far from the user eye the z=0 origin is set.

The keywords are convenience shorthands and match the following [`<percentage>`](percentage) values:

<table><thead><tr class="header"><th>Keyword</th><th>Value</th></tr></thead><tbody><tr class="odd"><td><code>left</code></td><td><code>0%</code></td></tr><tr class="even"><td><code>center</code></td><td><code>50%</code></td></tr><tr class="odd"><td><code>right</code></td><td><code>100%</code></td></tr><tr class="even"><td><code>top</code></td><td><code>0%</code></td></tr><tr class="odd"><td><code>bottom</code></td><td><code>100%</code></td></tr></tbody></table>

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>50% 50% 0</code></td></tr><tr class="even"><td>Applies to</td><td>transformable elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the size of bounding box</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>for <a href="length"><code>&lt;length&gt;</code></a> the absolute value, otherwise a percentage</td></tr><tr class="even"><td>Animation type</td><td>simple list of length, percentage, or calc</td></tr></tbody></table>

The initial value of `transform-origin` is `0 0` for all SVG elements except for root `<svg>` elements and `<svg>` elements that are a direct child of a [foreignObject](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/foreignObject), and whose `transform-origin` is `50% 50%`, like other CSS elements. See the [SVG transform-origin](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/transform-origin) attribute for more information.

## Formal syntax

    [ <length-percentage> | left | center | right | top | bottom ] | [ [ <length-percentage> | left | center | right ] && [ <length-percentage> | top | center | bottom ] ] <length>?where
    <length-percentage> = <length> | <percentage>

## Examples

### A demonstration of various transform values

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Code</th><th>Sample</th></tr></thead><tbody><tr class="odd"><td><p><code>transform: none;</code></p></td><td></td></tr><tr class="even"><td><p><code>transform: rotate(30deg);</code></p></td><td></td></tr><tr class="odd"><td><p><code>transform: rotate(30deg);      transform-origin: 0 0;</code></p></td><td></td></tr><tr class="even"><td><p><code>transform: rotate(30deg);      transform-origin: 100% 100%;</code></p></td><td></td></tr><tr class="odd"><td><p><code>transform: rotate(30deg);      transform-origin: -1em -3em;</code></p></td><td></td></tr><tr class="even"><td><p><code>transform: scale(1.7);</code></p></td><td></td></tr><tr class="odd"><td><p><code>transform: scale(1.7);      transform-origin: 0 0;</code></p></td><td></td></tr><tr class="even"><td><p><code>transform: scale(1.7);      transform-origin: 100% -30%;</code></p></td><td></td></tr><tr class="odd"><td><p><code>transform: skewX(50deg);      transform-origin: 100% -30%;</code></p></td><td></td></tr><tr class="even"><td><p><code>transform: skewY(50deg);      transform-origin: 100% -30%;</code></p></td><td></td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms/#transform-origin-property">CSS Transforms Level 1<br />
<span class="small">The definition of 'transform-origin' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`transform-origin`

36

1

12

12

16

3.5

49

44

10

9

23

15

12.1-15

10.5-15

9

2

37

≤37

36

18

16

4

49

44

24

15

12.1-15

11-14

9

1

3.0

1.0

`support_in_svg`

19

17

43

Keywords and percentages refer to the canvas instead of the object itself. See [bug 1209061](https://bugzil.la/1209061).

No

15

6

Only supported for transformations applied using the CSS `transform` property (e.g. `.className { transform: rotate(45deg); transform-origin: center; }`). It has no effect on transformations applied using the `transform` SVG attribute (e.g. `<rect style="transform-origin: center;" transform="rotate(45)" />`).

≤37

25

43

Keywords and percentages refer to the canvas instead of the object itself. See [bug 1209061](https://bugzil.la/1209061).

14

6

Only supported for transformations applied using the CSS `transform` property (e.g. `.className { transform: rotate(45deg); transform-origin: center; }`). It has no effect on transformations applied using the `transform` SVG attribute (e.g. `<rect style="transform-origin: center;" transform="rotate(45)" />`).

1.5

`three_value_syntax`

12

12

10

9

15

5

≤37

18

10

14

3.2

1.0

## See also

- [Using CSS transforms](css_transforms/using_css_transforms)
- <https://css-tricks.com/almanac/properties/t/transform-origin/>

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin</a>
