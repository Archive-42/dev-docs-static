# place-items

The [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) `place-items` [shorthand property](shorthand_properties) allows you to align items along both the block and inline directions at once (i.e. the [`align-items`](align-items) and [`justify-items`](justify-items) properties) in a relevant layout system such as [Grid](css_grid_layout) or [Flexbox](css_flexible_box_layout). If the second value is not set, the first value is also used for it.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`align-items`](align-items)
- [`justify-items`](justify-items)

## Syntax

    /* Keyword values */
    place-items: auto center;
    place-items: normal start;

    /* Positional alignment */
    place-items: center normal;
    place-items: start auto;
    place-items: end normal;
    place-items: self-start auto;
    place-items: self-end normal;
    place-items: flex-start auto;
    place-items: flex-end normal;
    place-items: left auto;
    place-items: right normal;

    /* Baseline alignment */
    place-items: baseline normal;
    place-items: first baseline auto;
    place-items: last baseline normal;
    place-items: stretch auto;

    /* Global values */
    place-items: inherit;
    place-items: initial;
    place-items: unset;

### Values

`auto`  
The value used is the value of the `justify-items` property of the parents box, unless the box has no parent, or is absolutely positioned, in these cases, `auto` represents `normal`.

`normal`  
The effect of this keyword is dependent of the layout mode we are in:

- In block-level layouts, the keyword is a synonym of `start`.
- In absolutely-positioned layouts, the keyword behaved like `start` on _replaced_ absolutely-positioned boxes, and as `stretch` on _all other_ absolutely-positioned boxes.
- In table cell layouts, this keyword has no meaning as this property is _ignored_.
- In flexbox layouts, this keyword has no meaning as this property is _ignored._
- In grid layouts, this keyword leads to a behavior similar to the one of `stretch`, except for boxes with an aspect ratio or an intrinsic sizes where it behaves like `start`.

`start`  
The item is packed flush to each other toward the start edge of the alignment container in the appropriate axis.

`end`  
The item is packed flush to each other toward the end edge of the alignment container in the appropriate axis.

`flex-start`  
The item is packed flush to each other toward the edge of the alignment container depending on the flex container's main-start or cross-start side.  
This only applies to flex layout items. For items that are not children of a flex container, this value is treated like `start`.

`flex-end`  
The item is packed flush to each other toward the edge of the alignment container depending on the flex container's main-end or cross-end side.  
This only applies to flex layout items. For items that are not children of a flex container, this value is treated like `end`.

`self-start`  
The item is packed flush to the edge of the alignment container of the start side of the item, in the appropriate axis.

`self-end`  
The item is packed flush to the edge of the alignment container of the end side of the item, in the appropriate axis.

`center`  
The items are packed flush to each other toward the center of the of the alignment container.

`left`  
The items are packed flush to each other toward the left edge of the alignment container. If the property’s axis is not parallel with the inline axis, this value behaves like `start`.

`right`  
The items are packed flush to each other toward the right edge of the alignment container in the appropriate axis. If the property’s axis is not parallel with the inline axis, this value behaves like `start`.

`baseline first baseline`  
`last baseline`  
Specifies participation in first- or last-baseline alignment: aligns the alignment baseline of the box’s first or last baseline set with the corresponding baseline in the shared first or last baseline set of all the boxes in its baseline-sharing group.  
The fallback alignment for `first baseline` is `start`, the one for `last baseline` is `end`.

`stretch`  
If the combined size of the items is less than the size of the alignment container, any `auto`-sized items have their size increased equally (not proportionally), while still respecting the constraints imposed by [`max-height`](max-height)/[`max-width`](max-width) (or equivalent functionality), so that the combined size exactly fills the alignment container.

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="align-items"><code>align-items</code></a>: <code>normal</code></li><li><a href="justify-items"><code>justify-items</code></a>: <code>legacy</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="align-items"><code>align-items</code></a>: as specified</li><li><a href="justify-items"><code>justify-items</code></a>: as specified</li></ul></td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <'align-items'> <'justify-items'>?

## Examples

### Placing items in a flex container

#### CSS

    #container {
      height:200px;
      width: 240px;
      place-items: center; /* You can change this value by selecting another option in the list */
      background-color: #8c8c8c;
    }

    .flex {
      display: flex;
      flex-wrap: wrap;
    }

    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, 50px);
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-align-3/#place-items-property">CSS Box Alignment Module Level 3<br />
<span class="small">The definition of 'place-items' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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
- The [`align-items`](align-items) property
- The [`align-self`](align-self) property
- The [`justify-items`](justify-items) property
- The [`justify-self`](justify-self) property

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/place-items" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/place-items</a>
