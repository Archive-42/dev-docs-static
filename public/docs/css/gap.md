# gap (grid-gap)

The `gap` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the gaps ([gutters](https://developer.mozilla.org/en-US/docs/Glossary/Gutters)) between rows and columns. It is a [shorthand](shorthand_properties) for [`row-gap`](row-gap) and [`column-gap`](column-gap).

## Syntax

    /* One <length> value */
    gap: 20px;
    gap: 1em;
    gap: 3vmin;
    gap: 0.5cm;

    /* One <percentage> value */
    gap: 16%;
    gap: 100%;

    /* Two <length> values */
    gap: 20px 10px;
    gap: 1em 0.5em;
    gap: 3vmin 2vmax;
    gap: 0.5cm 2mm;

    /* One or two <percentage> values */
    gap: 16% 100%;
    gap: 21px 82%;

    /* calc() values */
    gap: calc(10% + 20px);
    gap: calc(20px + 10%) calc(10% - 5px);

    /* Global values */
    gap: inherit;
    gap: initial;
    gap: unset;

This property is specified as a value for `<'row-gap'>` followed optionally by a value for `<'column-gap'>`. If `<'column-gap'>` is omitted, it’s set to the same value as `<'row-gap'>`.

`<'row-gap'>` and `<'column-gap'>` are each specified as a `<length>` or a `<percentage>`.

### Values

[`<length>`](length)  
Is the width of the gutter separating the grid lines.

[`<percentage>`](percentage)  
Is the width of the gutter separating the grid lines, relative to the dimension of the element.

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="row-gap"><code>row-gap</code></a>: <code>normal</code></li><li><a href="column-gap"><code>column-gap</code></a>: <code>normal</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>multi-column elements, flex containers, grid containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="row-gap"><code>row-gap</code></a>: as specified, with &lt;length&gt;s made absolute, and normal computing to zero except on multi-column elements</li><li><a href="column-gap"><code>column-gap</code></a>: as specified, with &lt;length&gt;s made absolute, and normal computing to zero except on multi-column elements</li></ul></td></tr><tr class="odd"><td>Animation type</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="row-gap"><code>row-gap</code></a>: a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</li><li><a href="column-gap"><code>column-gap</code></a>: a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</li></ul></td></tr></tbody></table>

## Formal syntax

    <'row-gap'> <'column-gap'>?

## Examples

### Flex layout

#### HTML

    <div id="flexbox">
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
    </div>

#### CSS

    #flexbox {
      display: flex;
      flex-wrap: wrap;
      width: 300px;
      gap: 20px 5px;
    }

    #flexbox > div {
      border: 1px solid green;
      background-color: lime;
      flex: 1 1 auto;
      width: 100px;
      height: 50px;

    }

#### Result

### Grid layout

#### HTML

    <div id="grid">
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
    </div>

#### CSS

    #grid {
      display: grid;
      height: 200px;
      grid-template: repeat(3, 1fr) / repeat(3, 1fr);
      gap: 20px 5px;
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
      gap created with the CSS <code>gap</code> property.
      Don't you think that's fun and exciting? I sure do!
    </p>

#### CSS

    .content-box {
      column-count: 3;
      gap: 40px;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-align-3/#propdef-gap">CSS Box Alignment Module Level 3<br />
<span class="small">The definition of 'gap' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`gap`

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

`gap`

66

57

16

16

61

52

No

53

44

10.1

12

66

57

66

57

61

52

47

43

10.3

12

9.0

7.0

`calc_values`

66

16

52

No

53

No

66

66

52

47

No

9.0

`percentage_values`

66

16

52

No

53

No

66

66

52

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

`gap`

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

- Related CSS properties: [`row-gap`](row-gap), [`column-gap`](column-gap)
- Grid Layout Guide: _[Basic concepts of grid layout - Gutters](css_grid_layout/basic_concepts_of_grid_layout#gutters)_

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/gap" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/gap</a>
