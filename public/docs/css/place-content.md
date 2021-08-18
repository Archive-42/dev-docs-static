# place-content

The `place-content` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [shorthand property](shorthand_properties) allows you to align content along both the block and inline directions at once (i.e. the [`align-content`](align-content) and [`justify-content`](justify-content) properties) in a relevant layout system such as [Grid](css_grid_layout) or [Flexbox](css_flexible_box_layout).

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`align-content`](align-content)
- [`justify-content`](justify-content)

## Syntax

    /* Positional alignment */
    /* align-content does not take left and right values */
    place-content: center start;
    place-content: start center;
    place-content: end left;
    place-content: flex-start center;
    place-content: flex-end center;

    /* Baseline alignment */
    /* justify-content does not take baseline values */
    place-content: baseline center;
    place-content: first baseline space-evenly;
    place-content: last baseline right;

    /* Distributed alignment */
    place-content: space-between space-evenly;
    place-content: space-around space-evenly;
    place-content: space-evenly stretch;
    place-content: stretch space-evenly;

    /* Global values */
    place-content: inherit;
    place-content: initial;
    place-content: unset;

The first value is the [`align-content`](align-content) property value, the second the [`justify-content`](justify-content) one.

**Important**: If the second value is not present, the first value is used for both, provided it is a valid value for both. If it is invalid for one or the other, the whole value will be invalid.

### Values

`start`  
The items are packed flush to each other toward the start edge of the alignment container in the appropriate axis.

`end`  
The items are packed flush to each other toward the end edge of the alignment container in the appropriate axis.

`flex-start`  
The items are packed flush to each other toward the edge of the alignment container depending on the flex container's main-start or cross-start side.  
This only applies to flex layout items. For items that are not children of a flex container, this value is treated like `start`.

`flex-end`  
The items are packed flush to each other toward the edge of the alignment container depending on the flex container's main-end or cross-end side.  
This only applies to flex layout items. For items that are not children of a flex container, this value is treated like `end`.

`center`  
The items are packed flush to each other toward the center of the alignment container.

`left`  
The items are packed flush to each other toward the left edge of the alignment container. If the property’s axis is not parallel with the inline axis, this value behaves like `start`.

`right`  
The items are packed flush to each other toward the right edge of the alignment container in the appropriate axis. If the property’s axis is not parallel with the inline axis, this value behaves like `start`.

`space-between`  
The items are evenly distributed within the alignment container. The spacing between each pair of adjacent items is the same. The first item is flush with the main-start edge, and the last item is flush with the main-end edge.

`baseline first baseline`  
`last baseline`  
Specifies participation in first- or last-baseline alignment: aligns the alignment baseline of the box’s first or last baseline set with the corresponding baseline in the shared first or last baseline set of all the boxes in its baseline-sharing group.  
The fallback alignment for `first baseline` is `start`, the one for `last baseline` is `end`.

`space-around`  
The items are evenly distributed within the alignment container. The spacing between each pair of adjacent items is the same. The empty space before the first and after the last item equals half of the space between each pair of adjacent items.

`space-evenly`  
The items are evenly distributed within the alignment container. The spacing between each pair of adjacent items, the main-start edge and the first item, and the main-end edge and the last item, are all exactly the same.

`stretch`  
If the combined size of the items is less than the size of the alignment container, any `auto`-sized items have their size increased equally (not proportionally), while still respecting the constraints imposed by [`max-height`](max-height)/[`max-width`](max-width) (or equivalent functionality), so that the combined size exactly fills the alignment container

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>multi-line flex containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <'align-content'> <'justify-content'>?

## Examples

### Placing content in a flex container

#### HTML

    <div id="container">
      <div class="small">Lorem</div>
      <div class="small">Lorem<br/>ipsum</div>
      <div class="large">Lorem</div>
      <div class="large">Lorem<br/>ipsum</div>
      <div class="large"></div>
      <div class="large"></div>
    </div>

#### CSS

    #container {
      display: flex;
      height:240px;
      width: 240px;
      flex-wrap: wrap;
      background-color: #8c8c8c;
      writing-mode: horizontal-tb; /* Can be changed in the live sample */
      direction: ltr; /* Can be changed in the live sample */
      place-content: flex-end center; /* Can be changed in the live sample */
    }

    div > div {
      border: 2px solid #8c8c8c;
      width: 50px;
      background-color: #a0c8ff;
    }

    .small {
      font-size: 12px;
      height: 40px;
    }

    .large {
      font-size: 14px;
      height: 50px;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-align-3/#propdef-place-content">CSS Box Alignment Module Level 3<br />
<span class="small">The definition of 'place content' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

Starting with version 60, you can only specify a single value if it is valid for both `align-content` and `justify-content`.

No

46

9

59

59

45

Starting with version 60, you can only specify a single value if it is valid for both `align-content` and `justify-content`.

43

9

7.0

`grid_context`

59

79

53

Starting with version 60, you can only specify a single value if it is valid for both `align-content` and `justify-content`.

No

46

11

59

59

53

Starting with version 60, you can only specify a single value if it is valid for both `align-content` and `justify-content`.

43

11

7.0

## See also

- CSS Flexbox Guide: _[Basic Concepts of Flexbox](css_flexible_box_layout/basic_concepts_of_flexbox)_
- CSS Flexbox Guide: _[Aligning items in a flex container](css_flexible_box_layout/aligning_items_in_a_flex_container)_
- CSS Grid Guide: _[Box alignment in CSS Grid layouts](css_grid_layout/box_alignment_in_css_grid_layout)_
- [CSS Box Alignment](css_box_alignment)
- The [`align-content`](align-content) property
- The [`justify-content`](justify-content) property

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/place-content" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/place-content</a>
