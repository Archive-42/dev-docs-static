# flex

The `flex` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [shorthand property](shorthand_properties) sets how a flex _item_ will grow or shrink to fit the space available in its flex container.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`flex-grow`](flex-grow)
- [`flex-shrink`](flex-shrink)
- [`flex-basis`](flex-basis)

## Syntax

    /* Keyword values */
    flex: auto;
    flex: initial;
    flex: none;

    /* One value, unitless number: flex-grow */
    flex: 2;

    /* One value, width/height: flex-basis */
    flex: 10em;
    flex: 30%;
    flex: min-content;

    /* Two values: flex-grow | flex-basis */
    flex: 1 30px;

    /* Two values: flex-grow | flex-shrink */
    flex: 2 2;

    /* Three values: flex-grow | flex-shrink | flex-basis */
    flex: 2 2 10%;

    /* Global values */
    flex: inherit;
    flex: initial;
    flex: unset;

The `flex` property may be specified using one, two, or three values.

- **One-value syntax:** the value must be one of:
  - a `<number>`: In this case it is interpreted as `flex: <number> 1 0`; the `<flex-shrink>` value is assumed to be 1 and the `<flex-basis>` value is assumed to be `0`.
  - one of the keywords: `none`, `auto`, or `initial`.
- **Two-value syntax:**
  - The first value must be:
    - a [`<number>`](number) and it is interpreted as `<flex-grow>`.
  - The second value must be one of:
    - a [`<number>`](number): then it is interpreted as `<flex-shrink>`.
    - a valid value for [`width`](width): then it is interpreted as `<flex-basis>`.
- **Three-value syntax:** the values must be in the following order:
  1.  a [`<number>`](number) for `<flex-grow>`.
  2.  a [`<number>`](number) for `<flex-shrink>`.
  3.  a valid value for [`width`](width) for `<flex-basis>`.

### Values

`initial`  
The item is sized according to its `width` and `height` properties. It shrinks to its minimum size to fit the container, but does not grow to absorb any extra free space in the flex container. This is equivalent to setting "`flex: 0 1 auto`".

`auto`  
The item is sized according to its `width` and `height` properties, but grows to absorb any extra free space in the flex container, and shrinks to its minimum size to fit the container. This is equivalent to setting "`flex: 1 1 auto`".

`none`  
The item is sized according to its `width` and `height` properties. It is fully inflexible: it neither shrinks nor grows in relation to the flex container. This is equivalent to setting "`flex: 0 0 auto`".

`<'flex-grow'>`  
Defines the [`flex-grow`](flex-grow) of the flex item. Negative values are considered invalid. Defaults to `1` when omitted. (initial is `0`)

`<'flex-shrink'>`  
Defines the [`flex-shrink`](flex-shrink) of the flex item. Negative values are considered invalid. Defaults to `1` when omitted. (initial is `1`)

`<'flex-basis'>`  
Defines the [`flex-basis`](flex-basis) of the flex item. A preferred size of `0` must have a unit to avoid being interpreted as a flexibility. Defaults to `0` when omitted. (initial is `auto`)

## Description

For most purposes, authors should set `flex` to one of the following values: `auto`, `initial`, `none`, or a positive unitless number. To see the effect of these values, try resizing the flex containers below:

By default flex items don't shrink below their minimum content size. To change this, set the item's [`min-width`](min-width) or [`min-height`](min-height).

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="flex-grow"><code>flex-grow</code></a>: <code>0</code></li><li><a href="flex-shrink"><code>flex-shrink</code></a>: <code>1</code></li><li><a href="flex-basis"><code>flex-basis</code></a>: <code>auto</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>flex items, including in-flow pseudo-elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="flex-grow"><code>flex-grow</code></a>: as specified</li><li><a href="flex-shrink"><code>flex-shrink</code></a>: as specified</li><li><a href="flex-basis"><code>flex-basis</code></a>: as specified, but with relative lengths converted into absolute lengths</li></ul></td></tr><tr class="odd"><td>Animation type</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="flex-grow"><code>flex-grow</code></a>: a <a href="number#interpolation">number</a></li><li><a href="flex-shrink"><code>flex-shrink</code></a>: a <a href="number#interpolation">number</a></li><li><a href="flex-basis"><code>flex-basis</code></a>: a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</li></ul></td></tr></tbody></table>

## Formal syntax

    none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]

## Examples

### Setting flex: auto

#### HTML

    <div id="flex-container">
      <div class="flex-item" id="flex">Flex box (click to toggle raw box)</div>
      <div class="raw-item" id="raw">Raw box</div>
    </div>

#### CSS

    #flex-container {
      display: flex;
      flex-direction: row;
    }

    #flex-container > .flex-item {
      flex: auto;
    }

    #flex-container > .raw-item {
      width: 5rem;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-flexbox-1/#flex-property">CSS Flexible Box Layout Module<br />
<span class="small">The definition of 'flex' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`flex`

29

21

12

12

20

\["Since Firefox 28, multi-line flexbox is supported.", "Before Firefox 32, Firefox wasn't able to animate values starting or stopping at `0`.", "Until Firefox 61, flex items that are sized according to their content are sized using [`fit-content`, not `max-content`](https://drafts.csswg.org/css-sizing-3/#column-sizing)."\]

49

11

\["Internet Explorer 11 ignores uses of [`calc()`](https://developer.mozilla.org/docs/Web/CSS/calc) in the `flex-basis` part of the `flex` syntax. This can be worked around by using the longhand properties instead of the shorthand. See [Flexbug \#8](https://github.com/philipwalton/flexbugs#8-flex-basis-doesnt-support-calc) for more info.", "Internet Explorer 11 considers a unitless value in the `flex-basis` part to be syntactically invalid (and will thus be ignored). A workaround is to always include a unit in the `flex-basis` part of the `flex` shorthand value. See [Flexbug \#4](https://github.com/philipwalton/flexbugs#4-flex-shorthand-declarations-with-unitless-flex-basis-values-are-ignored) for more info."\]

10

\["Internet Explorer 10 and 11 ignore uses of [`calc()`](https://developer.mozilla.org/docs/Web/CSS/calc) in the `flex-basis` part of the `flex` syntax. This can be worked around by using the longhand properties instead of the shorthand. See [Flexbug \#8](https://github.com/philipwalton/flexbugs#8-flex-basis-doesnt-support-calc) for more info.", "Internet Explorer 10 and 11 consider a unitless value in the `flex-basis` part to be syntactically invalid (and will thus be ignored). A workaround is to always include a unit in the `flex-basis` part of the `flex` shorthand value. See [Flexbug \#4](https://github.com/philipwalton/flexbugs#4-flex-shorthand-declarations-with-unitless-flex-basis-values-are-ignored) for more info."\]

12.1

9

6.1

4.4

≤37

29

25

20

\["Since Firefox 28, multi-line flexbox is supported.", "Before Firefox 32, Firefox wasn't able to animate values starting or stopping at `0`.", "Until Firefox 61, flex items that are sized according to their content are sized using [fit-content, not max-content](https://drafts.csswg.org/css-sizing-3/#column-sizing)."\]

49

12.1

9

7

2.0

1.5

## See also

- CSS Flexbox Guide: _[Basic Concepts of Flexbox](css_flexible_box_layout/basic_concepts_of_flexbox)_
- CSS Flexbox Guide: _[Controlling Ratios of flex items along the main axis](css_flexible_box_layout/controlling_ratios_of_flex_items_along_the_main_ax)_

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/flex" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/flex</a>
