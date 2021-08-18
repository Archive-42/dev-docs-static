# CSS Flexible Box Layout

**CSS Flexible Box Layout** is a module of [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) that defines a CSS box model optimized for user interface design, and the layout of items in one dimension. In the flex layout model, the children of a flex container can be laid out in any direction, and can “flex” their sizes, either growing to fill unused space or shrinking to avoid overflowing the parent. Both horizontal and vertical alignment of the children can be easily manipulated.

## Basic Example

In the following example a container has been set to `display: flex`, which means that the three child items become flex items. The value of `justify-content` has been set to `space-between` in order to space the items out evenly on the main axis. An equal amount of space is placed between each item with the left and right items being flush with the edges of the flex container. You can also see that the items are stretching on the cross axis, due to the default value of `align-items` being `stretch`. The items stretch to the height of the flex container, making them each appear as tall as the tallest item.

## Reference

### CSS Properties

- [`flex`](flex)
- [`flex-basis`](flex-basis)
- [`flex-direction`](flex-direction)
- [`flex-flow`](flex-flow)
- [`flex-grow`](flex-grow)
- [`flex-shrink`](flex-shrink)
- [`flex-wrap`](flex-wrap)
- [`order`](order)

### Alignment Properties

The properties `align-content`, `align-self`, `align-items` and `justify-content` initially appeared in the Flexbox specification, but are now defined in Box Alignment. The Flexbox spec now refers to the Box Alignment specification for up to date definitions. Also additional alignment properties are now defined in Box Alignment.

- [`justify-content`](justify-content)
- [`align-content`](align-content)
- [`align-items`](align-items)
- [`align-self`](align-self)
- [`place-content`](place-content)
- [`place-items`](place-items)
- [`row-gap`](row-gap)
- [`column-gap`](column-gap)
- [`gap`](gap)

### Glossary entries

- [Flexbox](https://developer.mozilla.org/en-US/docs/Glossary/Flexbox)
- [Flex Container](https://developer.mozilla.org/en-US/docs/Glossary/Flex_Container)
- [Flex Item](https://developer.mozilla.org/en-US/docs/Glossary/Flex_Item)
- [Main Axis](https://developer.mozilla.org/en-US/docs/Glossary/Main_Axis)
- [Cross Axis](https://developer.mozilla.org/en-US/docs/Glossary/Cross_Axis)
- [Flex](https://developer.mozilla.org/en-US/docs/Glossary/Flex)

## Guides

[Basic Concepts of Flexbox](css_flexible_box_layout/basic_concepts_of_flexbox)  
An overview of the features of Flexbox

[Relationship of Flexbox to other layout methods](css_flexible_box_layout/relationship_of_flexbox_to_other_layout_methods)  
How Flexbox relates to other layout methods, and other CSS specifications

[Aligning items in a flex container](css_flexible_box_layout/aligning_items_in_a_flex_container)  
How the Box Alignment properties work with Flexbox.

[Ordering flex items](css_flexible_box_layout/ordering_flex_items)  
Explaining the different ways to change the order and direction of items, and covering the potential issues in doing so.

[Controlling Ratios of flex items along the main axis](css_flexible_box_layout/controlling_ratios_of_flex_items_along_the_main_ax)  
Explaining the flex-grow, flex-shrink and flex-basis properties.

[Mastering wrapping of flex items](css_flexible_box_layout/mastering_wrapping_of_flex_items)  
How to create flex containers with multiple lines and control the display of the items in those lines.

[Typical use cases of Flexbox](css_flexible_box_layout/typical_use_cases_of_flexbox)  
Common design patterns that are typical Flexbox use cases.

[Backwards compatibility of Flexbox](css_flexible_box_layout/backwards_compatibility_of_flexbox)  
Browser status of Flexbox, interoperability issues and supporting older browsers and versions of the spec

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-flexbox-1/">CSS Flexible Box Layout Module</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## See also

[Flexbugs](https://github.com/philipwalton/flexbugs)  
a community-curated list of Flexbox browser bugs and workarounds

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout</a>
