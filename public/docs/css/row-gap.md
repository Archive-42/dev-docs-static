# row-gap (grid-row-gap)

The `row-gap` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the size of the gap ([gutter](https://developer.mozilla.org/en-US/docs/Glossary/Gutters)) between an element's grid rows.

## Syntax

    /* <length> values */
    row-gap: 20px;
    row-gap: 1em;
    row-gap: 3vmin;
    row-gap: 0.5cm;

    /* <percentage> value */
    row-gap: 10%;

    /* Global values */
    row-gap: inherit;
    row-gap: initial;
    row-gap: unset;

### Values

`<length-percentage>`  
Is the width of the gutter separating the rows. [`<percentage>`](percentage) values are relative to the dimension of the element.

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
      <div></div>
      <div></div>
      <div></div>
    </div>

#### CSS

    #flexbox {
      display: flex;
      flex-wrap: wrap;
      width: 300px;
      row-gap: 20px;
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
    </div>

#### CSS

    #grid {
      display: grid;
      height: 200px;
      grid-template-columns: 200px;
      grid-template-rows: repeat(3, 1fr);
      row-gap: 20px;
    }

    #grid > div {
      border: 1px solid green;
      background-color: lime;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-align-3/#propdef-row-gap">CSS Box Alignment Module Level 3<br />
<span class="small">The definition of 'row-gap' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`row-gap`

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

`row-gap`

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

## See also

- Related CSS properties: [`column-gap`](column-gap), [`gap`](gap)
- Grid Layout Guide: _[Basic concepts of grid layout - Gutters](css_grid_layout/basic_concepts_of_grid_layout#gutters)_

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/row-gap" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/row-gap</a>
