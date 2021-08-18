# Introduction to the CSS basic box model

When laying out a document, the browser's rendering engine represents each element as a rectangular box according to the standard **CSS basic box model**. CSS determines the size, position, and properties (color, background, border size, etc.) of these boxes.

Every box is composed of four parts (or _areas_), defined by their respective edges: the _content edge_, _padding edge_, _border edge_, and _margin edge_.

<img src="data:image/png;base64,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" alt="CSS Box model" width="548" height="384" />

The **content area**, bounded by the content edge, contains the "real" content of the element, such as text, an image, or a video player. Its dimensions are the _content width_ (or _content-box width_) and the _content height_ (or _content-box height_). It often has a background color or background image.

If the [`box-sizing`](../box-sizing) property is set to `content-box` (default) and if the element is a block element, the content area's size can be explicitly defined with the [`width`](../width), [`min-width`](../min-width), [`max-width`](../max-width), [`height`](../height), [`min-height`](../min-height), and [`max-height`](../max-height) properties.

The **padding area**, bounded by the padding edge, extends the content area to include the element's padding. Its dimensions are the _padding-box width_ and the _padding-box height_.

The thickness of the padding is determined by the [`padding-top`](../padding-top), [`padding-right`](../padding-right), [`padding-bottom`](../padding-bottom), [`padding-left`](../padding-left), and shorthand [`padding`](../padding) properties.

The **border area**, bounded by the border edge, extends the padding area to include the element's borders. Its dimensions are the _border-box width_ and the _border-box height_.

The thickness of the borders are determined by the [`border-width`](../border-width) and shorthand [`border`](../border) properties. If the [`box-sizing`](../box-sizing) property is set to `border-box`, the border area's size can be explicitly defined with the [`width`](../width), [`min-width`](../min-width), [`max-width`](../max-width), [`height`](../height), [`min-height`](../min-height), and [`max-height`](../max-height) properties. When there is a background ([`background-color`](../background-color) or [`background-image`](../background-image)) set on a box, it extends to the outer edge of the border (i.e. extends underneath the border in z-ordering). This default behavior can be altered with the [`background-clip`](../background-clip) css property.

The **margin area**, bounded by the margin edge, extends the border area to include an empty area used to separate the element from its neighbors. Its dimensions are the _margin-box width_ and the _margin-box height_.

The size of the margin area is determined by the [`margin-top`](../margin-top), [`margin-right`](../margin-right), [`margin-bottom`](../margin-bottom), [`margin-left`](../margin-left), and shorthand [`margin`](../margin) properties. When [margin collapsing](mastering_margin_collapsing) occurs, the margin area is not clearly defined since margins are shared between boxes.

Finally, note that for non-replaced inline elements, the amount of space taken up (the contribution to the height of the line) is determined by the [`line-height`](../line-height) property, even though the borders and padding are still displayed around the content.

## See also

- [Layout and the containing block](../containing_block)
- [Introducing the CSS Cascade](../cascade)
- [Cascade and inheritance](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-box-3/#intro">CSS Basic Box Model</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/box.html#box-dimensions">CSS Level 2 (Revision 1)</a></td><td><span class="spec-rec">Recommendation</span></td><td>Though more precisely worded, there is no practical change.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#formatting-model">CSS Level 1</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## See also

- CSS Key Concepts: [CSS syntax](../syntax), [at-rule](../at-rule), [comments](../comments), [specificity](../specificity) and [inheritance](../inheritance), the [box](introduction_to_the_css_box_model), [layout modes](../layout_mode) and [visual formatting models](../visual_formatting_model), and [margin collapsing](mastering_margin_collapsing), or the [initial](../initial_value), [computed](../computed_value), [resolved](../resolved_value), [specified](../specified_value), [used](../used_value), and [actual](../actual_value) values. Definitions of [value syntax](../value_definition_syntax), [shorthand properties](../shorthand_properties) and [replaced elements](../replaced_element).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model</a>