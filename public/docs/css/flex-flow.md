# flex-flow

The `flex-flow` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [shorthand property](shorthand_properties) specifies the direction of a flex container, as well as its wrapping behavior.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`flex-direction`](flex-direction)
- [`flex-wrap`](flex-wrap)

## Syntax

    /* flex-flow: <'flex-direction'> */
    flex-flow: row;
    flex-flow: row-reverse;
    flex-flow: column;
    flex-flow: column-reverse;

    /* flex-flow: <'flex-wrap'> */
    flex-flow: nowrap;
    flex-flow: wrap;
    flex-flow: wrap-reverse;

    /* flex-flow: <'flex-direction'> and <'flex-wrap'> */
    flex-flow: row nowrap;
    flex-flow: column wrap;
    flex-flow: column-reverse wrap-reverse;

    /* Global values */
    flex-flow: inherit;
    flex-flow: initial;
    flex-flow: unset;

### Values

See [`flex-direction`](flex-direction) and [`flex-wrap`](flex-wrap) for details on the values.

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="flex-direction"><code>flex-direction</code></a>: <code>row</code></li><li><a href="flex-wrap"><code>flex-wrap</code></a>: <code>nowrap</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>flex containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="flex-direction"><code>flex-direction</code></a>: as specified</li><li><a href="flex-wrap"><code>flex-wrap</code></a>: as specified</li></ul></td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <'flex-direction'> || <'flex-wrap'>

## Examples

### Setting column-reverse and wrap

    element {
      /* Main-axis is the block direction with reversed main-start and main-end. Flex items are laid out in multiple lines */
      flex-flow: column-reverse wrap;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-flexbox-1/#flex-flow-property">CSS Flexible Box Layout Module<br />
<span class="small">The definition of 'flex-flow' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`flex-flow`

29

21

12

28

49

11

12.1

15

9

6.1

4.4

≤37

29

25

28

49

12.1

14

9

7

2.0

1.5

## See also

- CSS Flexbox Guide: _[Basic Concepts of Flexbox](css_flexible_box_layout/basic_concepts_of_flexbox)_
- CSS Flexbox Guide: _[Ordering flex items](css_flexible_box_layout/ordering_flex_items)_

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/flex-flow" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/flex-flow</a>
