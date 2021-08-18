# Layout mode

A [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) **layout mode**, sometimes called _layout_, is an algorithm that determines the position and size of boxes based on the way they interact with their sibling and ancestor boxes. There are several of them:

- _[Normal flow](css_flow_layout)_ — all elements are part of normal flow until you do something to take them out of it. Normal flow includes _block layout_, designed for laying out boxes such as paragraphs and _inline layout_, which lays out inline items such as text.
- [_Table layout_](css_table), designed for laying out tables.
- _Float layout_, designed to cause an item to position itself left or right with the rest of the content in normal flow wrapping around it.
- [_Positioned layout_](css_positioning), designed for positioning elements without much interaction with other elements.
- [_Multi-column layout_](css_columns), designed for laying content out in columns as in a newspaper.
- [_Flexible box layout_](css_flexible_box_layout), designed for laying out complex pages that can be resized smoothly.
- [_Grid layout_](css_grid_layout), designed for laying out elements relative to a fixed grid.

**Note:** Not all [CSS properties](index) apply to all _layout modes_. Most of them apply to one or two of them and have no effect if they are set on an element participating in another layout mode.

## See also

- CSS Key Concepts: [CSS syntax](syntax), [at-rule](at-rule), [comments](comments), [specificity](specificity) and [inheritance](inheritance), the [box](css_box_model/introduction_to_the_css_box_model), [layout modes](layout_mode) and [visual formatting models](visual_formatting_model), and [margin collapsing](css_box_model/mastering_margin_collapsing), or the [initial](initial_value), [computed](computed_value), [resolved](resolved_value), [specified](specified_value), [used](used_value), and [actual](actual_value) values. Definitions of [value syntax](value_definition_syntax), [shorthand properties](shorthand_properties) and [replaced elements](replaced_element).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_mode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_mode</a>
