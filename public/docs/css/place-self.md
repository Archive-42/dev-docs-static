# place-self

The `place-self` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [shorthand property](shorthand_properties) allows you to align an individual item in both the block and inline directions at once (i.e. the [`align-self`](align-self) and [`justify-self`](justify-self) properties) in a relevant layout system such as [Grid](css_grid_layout) or [Flexbox](css_flexible_box_layout). If the second value is not present, the first value is also used for it.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`align-self`](align-self)
- [`justify-self`](justify-self)

## Syntax

    /* Keyword values */
    place-self: auto center;
    place-self: normal start;

    /* Positional alignment */
    place-self: center normal;
    place-self: start auto;
    place-self: end normal;
    place-self: self-start auto;
    place-self: self-end normal;
    place-self: flex-start auto;
    place-self: flex-end normal;
    place-self: left auto;
    place-self: right normal;

    /* Baseline alignment */
    place-self: baseline normal;
    place-self: first baseline auto;
    place-self: last baseline normal;
    place-self: stretch auto;

    /* Global values */
    place-self: inherit;
    place-self: initial;
    place-self: unset;

### Values

`auto`  
Computes to the parent's [`align-items`](align-items) value.

`normal`  
The effect of this keyword is dependent of the layout mode we are in:

- In absolutely-positioned layouts, the keyword behaves like `start` on _replaced_ absolutely-positioned boxes, and as `stretch` on _all other_ absolutely-positioned boxes.
- In static position of absolutely-positioned layouts, the keyword behaves as `stretch`.
- For flex items, the keyword behaves as `stretch`.
- For grid items, this keyword leads to a behavior similar to the one of `stretch`, except for boxes with an aspect ratio or an intrinsic sizes where it behaves like `start`.
- The property doesn't apply to block-level boxes, and to table cells.

`self-start`  
Aligns the items to be flush with the edge of the alignment container corresponding to the item's start side in the cross axis.

`self-end`  
Aligns the items to be flush with the edge of the alignment container corresponding to the item's end side in the cross axis.

`flex-start`  
The cross-start margin edge of the flex item is flushed with the cross-start edge of the line.

`flex-end`  
The cross-end margin edge of the flex item is flushed with the cross-end edge of the line.

`center`  
The flex item's margin box is centered within the line on the cross-axis. If the cross-size of the item is larger than the flex container, it will overflow equally in both directions.

`baseline first baseline`  
`last baseline`  
Specifies participation in first- or last-baseline alignment: aligns the alignment baseline of the box’s first or last baseline set with the corresponding baseline in the shared first or last baseline set of all the boxes in its baseline-sharing group.  
The fallback alignment for `first baseline` is `start`, the one for `last baseline` is `end`.

`stretch`  
If the combined size of the items along the cross axis is less than the size of the alignment container and the item is `auto`-sized, its size is increased equally (not proportionally), while still respecting the constraints imposed by [`max-height`](max-height)/[`max-width`](max-width) (or equivalent functionality), so that the combined size of all `auto`-sized items exactly fills the alignment container along the cross axis.

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="align-self"><code>align-self</code></a>: <code>auto</code></li><li><a href="justify-self"><code>justify-self</code></a>: <code>auto</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>block-level boxes, absolutely-positioned boxes, and grid items</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="align-self"><code>align-self</code></a>: <code>auto</code> computes to itself on absolutely-positioned elements, and to the computed value of <a href="align-items"><code>align-items</code></a> on the parent (minus any legacy keywords) on all other boxes, or <code>start</code> if the box has no parent. Its behavior depends on the layout model, as described for <a href="justify-self"><code>justify-self</code></a>. Otherwise the specified value.</li><li><a href="justify-self"><code>justify-self</code></a>: as specified</li></ul></td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <'align-self'> <'justify-self'>?

## Examples

### Simple demonstration

In the following example we have a simple 2 x 2 grid layout. Initially the grid container has `justify-items` and `align-items` values of `stretch` — the defaults — which causes the grid items to stretch across the entire width of their cells.

The second, third, and fourth grid items are then given different values of `place-self`, to show how these override the default placements. These values cause the grid items to span only as wide/tall as their content width/height, and align in different positions across their cells, in the block and inline directions.

#### HTML

    <article class="container">
      <span>First</span>
      <span>Second</span>
      <span>Third</span>
      <span>Fourth</span>
    </article>

#### CSS

    html {
      font-family: helvetica, arial, sans-serif;
      letter-spacing: 1px;
    }

    article {
      background-color: red;
      display: grid;
      grid-template-columns: 1fr 1fr;
      grid-auto-rows: 80px;
      grid-gap: 10px;
      width: 300px;
    }

    span:nth-child(2) {
      place-self: start center;
    }

    span:nth-child(3) {
      place-self: center start;
    }

    span:nth-child(4) {
      place-self: end;
    }

    article span {
      background-color: black;
      color: white;
      margin: 1px;
      text-align: center;
    }

    article, span {
      padding: 10px;
      border-radius: 7px;
    }

    article {
      margin: 20px;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-align-3/#place-self-property">CSS Box Alignment Module Level 3<br />
<span class="small">The definition of 'place-self' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`flex_context`

59

79

45

No

46

11

59

59

45

43

11

7.0

`grid_context`

59

79

45

No

46

11

59

59

45

43

11

7.0

## See also

- CSS Flexbox Guide: _[Basic Concepts of Flexbox](css_flexible_box_layout/basic_concepts_of_flexbox)_
- CSS Flexbox Guide: _[Aligning items in a flex container](css_flexible_box_layout/aligning_items_in_a_flex_container)_
- CSS Grid Guide: _[Box alignment in CSS Grid layouts](css_grid_layout/box_alignment_in_css_grid_layout)_
- [CSS Box Alignment](css_box_alignment)
- The [`align-self`](align-self) property
- The [`justify-self`](justify-self) property

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/place-self" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/place-self</a>
