# CSS Multi-column Layout

**CSS Multi-column Layout** is a module of CSS that adds support for multi-column layouts. Support is included for establishing the number of columns in a layout, as well as how content should flow from column to column, gap sizes between columns, and column dividing lines (known as column rules) along with their appearance.

## Basic example

In the following example the [`column-count`](column-count) property has been applied to the element with a class of container. As the value of `column-count` is `3`, the content is arranged into 3 columns of equal size.

## Relationship to Fragmentation

Multiple-column Layout is closely related to [Paged Media](css_pages), in that each column box becomes a fragment, much like a printed page becomes a fragment of an overall document. Therefore the properties now defined in the [CSS Fragmentation](css_fragmentation) specification are required in order to control how content breaks between columns.

## Reference

### Multiple-column Layout Properties

- [`column-count`](column-count)
- [`column-fill`](column-fill)
- [`column-gap`](column-gap)
- [`column-rule`](column-rule)
- [`column-rule-color`](column-rule-color)
- [`column-rule-style`](column-rule-style)
- [`column-rule-width`](column-rule-width)
- [`column-span`](column-span)
- [`column-width`](column-width)
- [`columns`](columns)

### Related CSS Fragmentation Properties

- [`break-after`](break-after)
- [`break-before`](break-before)
- [`break-inside`](break-inside)
- [`orphans`](orphans)
- [`widows`](widows)

## Guides

[Basic Concepts of Multicol](css_columns/basic_concepts_of_multicol)  
An overview of the Multiple-column Layout specification

[Styling Columns](css_columns/styling_columns)  
How to use column rules and manage the spacing between columns.

[Spanning and Balancing](css_columns/spanning_columns)  
How to make elements span across all columns and controlling the way columns are filled.

[Handling Overflow in Multicol](css_columns/handling_overflow_in_multicol)  
What happens when an item overflows the column it is in and what happens when there is too much columned content to fit a container.

[Content Breaks in Multicol](css_columns/handling_content_breaks_in_multicol)  
Introduction to the Fragmentation specification and how to control where column content breaks.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-multicol-1/">CSS Multi-column Layout Module</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

## See also

Other CSS layout technologies include:

- [CSS Flexible Box Layout](css_flexible_box_layout) (CSS flexbox)
- [CSS Grid Layout](css_grid_layout)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Columns" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Columns</a>
