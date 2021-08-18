# column-gap (grid-column-gap)

The `column-gap` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the size of the gap ([gutter](https://developer.mozilla.org/en-US/docs/Glossary/Gutters)) between an element's columns.

Initially a part of [Multi-column Layout](css_columns), the definition of `column-gap` has been broadened to include multiple layout methods. Now specified in [Box Alignment](css_box_alignment), it may be used in Multi-column, Flexible Box, and Grid layouts.

## Syntax

    /* Keyword value */
    column-gap: normal;

    /* <length> values */
    column-gap: 3px;
    column-gap: 2.5em;

    /* <percentage> value */
    column-gap: 3%;

    /* Global values */
    column-gap: inherit;
    column-gap: initial;
    column-gap: unset;

The `column-gap` property is specified as one of the values listed below.

### Values

`normal`  
The browser's default spacing is used between columns. For multi-column layout this is specified as `1em`. For all other layout types it is 0.

[`<length>`](length)  
The size of the gap between columns, defined as a [`<length>`](length). The [`<length>`](length) property's value must be non-negative.

[`<percentage>`](percentage)  
The size of the gap between columns, defined as a [`<percentage>`](percentage). The [`<percentage>`](percentage) property's value must be non-negative.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>multi-column elements, flex containers, grid containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to corresponding dimension of the content area</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as specified, with &lt;length&gt;s made absolute, and normal computing to zero except on multi-column elements</td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    normal | <length-percentage>where
    <length-percentage> = <length> | <percentage>

## Examples

### Flex layout

#### HTML

    <div id="flexbox">
      <div></div>
      <div></div>
      <div></div>
    </div>

#### CSS

    #flexbox {
      display: flex;
      height: 100px;
      column-gap: 20px;
    }

    #flexbox > div {
      border: 1px solid green;
      background-color: lime;
      flex: auto;
    }

#### Result

### Grid layout

#### HTML

    <div id="grid">
      <div></div>
      <div></div>
      <div></div>
    </div>

#### CSS

    #grid {
      display: grid;
      height: 100px;
      grid-template-columns: repeat(3, 1fr);
      grid-template-rows: 100px;
      column-gap: 20px;
    }

    #grid > div {
      border: 1px solid green;
      background-color: lime;
    }

#### Result

### Multi-column layout

#### HTML

    <p class="content-box">
      This is some multi-column text with a 40px column
      gap created with the CSS `column-gap` property.
      Don't you think that's fun and exciting? I sure do!
    </p>

#### CSS

    .content-box {
      column-count: 3;
      column-gap: 40px;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-align-3/#column-row-gap">CSS Box Alignment Module Level 3<br />
<span class="small">The definition of 'column-gap' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Applies to grid and flexbox</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-grid/#gutters">CSS Grid Layout<br />
<span class="small">The definition of 'column-gap' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Specifies how this property affects grid layouts</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/css-multicol-1/#column-gap">CSS Multi-column Layout Module<br />
<span class="small">The definition of 'column-gap' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`column-gap`

50

1

12

12

52

1.5-74

Before Firefox 3, the default value for the `normal` keyword was `0` and not `1em`.

10

37

15

11.1-15

10

3

50

≤37

50

18

52

4

37

14

11.1-14

10

3

5.0

1.0

`calc_values`

66

16

61

No

53

No

66

66

61

47

No

9.0

`percentage_values`

66

16

61

No

53

No

66

66

61

47

No

9.0

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

`column-gap`

66

57

16

16

61

52

No

53

44

12.1

10.1

66

57

66

57

61

52

47

43

12

10.3

9.0

6.0

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

`column-gap`

84

84

63

No

70

14.1

84

84

63

No

14.5

No

BCD tables only load in the browser

### Support in Grid layout

BCD tables only load in the browser

### Support in Multi-column layout

BCD tables only load in the browser

## See also

- Related CSS properties: [`row-gap`](row-gap), [`gap`](gap)
- Grid Layout Guide: _[Basic concepts of grid layout - Gutters](css_grid_layout/basic_concepts_of_grid_layout#gutters)_
- Multi-column Layout Guide: _[Styling Columns](css_columns/styling_columns)_

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap</a>
