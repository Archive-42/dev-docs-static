# min-height

The `min-height` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the minimum height of an element. It prevents the [used value](used_value) of the [`height`](height) property from becoming smaller than the value specified for `min-height`.

The element's height is set to the value of `min-height` whenever `min-height` is larger than [`max-height`](max-height) or [`height`](height).

## Syntax

    /* <length> value */
    min-height: 3.5em;

    /* <percentage> value */
    min-height: 10%;

    /* Keyword values */
    min-height: max-content;
    min-height: min-content;
    min-height: fit-content(20em);

    /* Global values */
    min-height: inherit;
    min-height: initial;
    min-height: unset;

### Values

[`<length>`](length)  
Defines the `min-height` as an absolute value.

[`<percentage>`](percentage)  
Defines the `min-height` as a percentage of the containing block's height.

`auto`  
The browser will calculate and select a `min-height` for the specified element.

`max-content`  
The intrinsic preferred `min-height`.

`min-content`  
The intrinsic minimum `min-height`.

`fit-content(<length-percentage>`)  
Uses the `fit-content` formula with the available space replaced by the specified argument, i.e. `min(max-content, max(min-content, argument))`.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>all elements but non-replaced inline elements, table columns, and column groups</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>The percentage is calculated with respect to the height of the generated box's containing block. If the height of the containing block is not specified explicitly (i.e., it depends on content height), and this element is not absolutely positioned, the percentage value is treated as <code>0</code>.</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>the percentage as specified or the absolute length</td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    auto | <length> | <percentage> | min-content | max-content | fit-content | fit-content(<length-percentage>)where
    <length-percentage> = <length> | <percentage>

## Examples

### Setting min-height

    table { min-height: 75%; }

    form { min-height: 0; }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-sizing-4/#width-height-keywords">CSS Box Sizing Module Level 4<br />
<span class="small">The definition of 'min-height' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-sizing-3/#width-height-keywords">CSS Box Sizing Module Level 3<br />
<span class="small">The definition of 'min-height' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds the <code>max-content</code>, <code>min-content</code>, <code>fit-content</code> keywords.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/visudet.html#min-max-heights">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'min-height' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`min-height`

1

12

3

CSS 2.1 leaves the behavior of `min-height` with [`table`](https://developer.mozilla.org/docs/Web/HTML/Element/table) undefined. Firefox supports applying `min-height` to `table` elements.

7

In Internet Explorer 10 and 11, a `min-height` declaration on a column-direction flex container doesn't apply to the container's flex items. See [Flexbug \#3](https://github.com/philipwalton/flexbugs#3-min-height-on-a-column-flex-container-wont-apply-to-its-flex-items) for more info.

4

CSS 2.1 leaves the behavior of `min-height` with [`table`](https://developer.mozilla.org/docs/Web/HTML/Element/table) undefined. Opera supports applying `min-height` to `table` elements.

1.3

4.4

18

4

CSS 2.1 leaves the behavior of `min-height` with [`table`](https://developer.mozilla.org/docs/Web/HTML/Element/table) undefined. Firefox supports applying `min-height` to `table` elements.

14

1

1.0

`auto`

21

79

16-22

Firefox 18 and later used `auto` as the initial value for `min-height`.

No

12.1

No

37

25

16-22

Firefox 18 and later used `auto` as the initial value for `min-height`.

14

No

1.5

`fit-content`

46

25

79

79

3

Firefox implements the definitions given in CSS3 Basic Box. This defines `available` and not `fit-available`. Also, the definition of `fit-content` is simpler than in CSS3 Sizing.

No

44

11

6.1

2

46

≤37

46

4

Firefox implements the definitions given in CSS3 Basic Box. This defines `available` and not `fit-available`. Also, the definition of `fit-content` is simpler than in CSS3 Sizing.

43

11

6.1

1

5.0

`max-content`

46

79

66

3

No

44

11

9

46

46

66

4

43

11

9

5.0

`min-content`

46

79

66

3

No

44

11

9

46

46

66

4

43

11

9

5.0

`stretch`

28

79

No

No

15

9

4.4

28

No

15

9

1.5

## See also

- [The box model](css_box_model/introduction_to_the_css_box_model), [`box-sizing`](box-sizing)
- [`height`](height), [`max-height`](max-height)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/min-height" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/min-height</a>
