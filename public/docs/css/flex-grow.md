# flex-grow

The `flex-grow` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the flex grow factor of a flex item's [main size](https://www.w3.org/TR/css-flexbox/#main-size).

## Syntax

    /* <number> values */
    flex-grow: 3;
    flex-grow: 0.6;

    /* Global values */
    flex-grow: inherit;
    flex-grow: initial;
    flex-grow: unset;

The `flex-grow` property is specified as a single `<number>`.

### Values

`<number>`  
See [`<number>`](number). Negative values are invalid. Defaults to 0.

## Description

This property specifies how much of the remaining space in the flex container should be assigned to the item (the flex grow factor).

The [main size](https://www.w3.org/TR/css-flexbox/#main-size) is either width or height of the item which is dependent on the [`flex-direction`](flex-direction) value.

The remaining space is the size of the flex container minus the size of all flex items' sizes together. If all sibling items have the same flex grow factor, then all items will receive the same share of remaining space, otherwise it is distributed according to the ratio defined by the different flex grow factors.

`flex-grow` is used alongside the other flex properties [`flex-shrink`](flex-shrink) and [`flex-basis`](flex-basis), and normally defined using the [`flex`](flex) shorthand to ensure all values are set.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>flex items, including in-flow pseudo-elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="number#interpolation">number</a></td></tr></tbody></table>

## Formal syntax

    <number>

## Examples

### Setting flex item grow factor

#### HTML

    <h4>This is a Flex-Grow</h4>
    <h5>A,B,C and F are flex-grow:1 . D and E are flex-grow:2 .</h5>
    <div id="content">
      <div class="box" style="background-color:red;">A</div>
      <div class="box" style="background-color:lightblue;">B</div>
      <div class="box" style="background-color:yellow;">C</div>
      <div class="box1" style="background-color:brown;">D</div>
      <div class="box1" style="background-color:lightgreen;">E</div>
      <div class="box" style="background-color:brown;">F</div>
    </div>

#### CSS

    #content {
      display: flex;

      justify-content: space-around;
      flex-flow: row wrap;
      align-items: stretch;
    }

    .box {
      flex-grow: 1;
      border: 3px solid rgba(0,0,0,.2);
    }

    .box1 {
      flex-grow: 2;
      border: 3px solid rgba(0,0,0,.2);
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-flexbox-1/#flex-grow-property">CSS Flexible Box Layout Module<br />
<span class="small">The definition of 'flex-grow' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`flex-grow`

29

22

12

12

20

Since Firefox 28, multi-line flexbox is supported.

11

10

12.1

15

9

6.1

4.4

≤37

29

25

20

Since Firefox 28, multi-line flexbox is supported.

12.1

14

9

7

2.0

1.5

`less_than_zero_animate`

49

79

32

Before Firefox 32, Firefox wasn't able to animate values starting or stopping at `0`.

No

36

No

49

49

32

Before Firefox 32, Firefox wasn't able to animate values starting or stopping at `0`.

36

No

5.0

## See also

- CSS Flexbox Guide: _[Basic Concepts of Flexbox](css_flexible_box_layout/basic_concepts_of_flexbox)_
- CSS Flexbox Guide: _[Controlling Ratios of flex items along the main axis](css_flexible_box_layout/controlling_ratios_of_flex_items_along_the_main_ax)_
- [\`flex-grow\` is weird. Or is it?](https://css-tricks.com/flex-grow-is-weird/) article by Manuel Matuzovic on CSS-Tricks, which illustrates how flex-grow works

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/flex-grow" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/flex-grow</a>
