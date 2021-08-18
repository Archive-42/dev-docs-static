# Handling content breaks in multicol

Content is broken between column boxes in multiple-column layout in the same way that it is broken between pages in paged media. In both contexts we control where and how things break by using properties of the CSS Fragmentation specification. In this guide we see how Fragmentation works in multicol.

## Fragmentation basics

The [CSS Fragmentation specification](https://www.w3.org/TR/css-break-3/) details how content breaks between the fragmentation containers, or _fragmentainers_. In multicol, the fragmentainer is the column box.

A column box can contain other markup and there are many places where a break would not be ideal. For example, we would generally prefer that the figcaption of an image not be separated into a new column away from the image it refers to and ending a column with a heading looks strange. The fragmentation properties give us ways to exercise some control over this.

There are various places we might want to control our breaks:

- Breaks inside boxes, for example inside a figure element.
- Breaks before and after boxes, which would include our heading example above.
- Breaks between lines.

## Breaks inside boxes

To control breaks inside boxes use the [`break-inside`](../break-inside) property. This property takes values of:

- `auto`
- `avoid`
- `avoid-page`
- `avoid-column`
- `avoid-region`

In the example below, we have applied break-inside to the figure element to prevent the caption from becoming separated from the image.

## Breaks before and after boxes

The [`break-before`](../break-before) and [`break-after`](../break-after) properties are used to control breaks before and after elements. They take the following values when in a multicol context:

- auto
- avoid
- avoid-column
- column

In this next example, we are forcing a column break before an `h2` element.

## Breaks between lines

The [`orphans`](../orphans) and [`widows`](../widows) properties are also useful. The orphans property controls the number of lines left on their own at the end of a fragment. The widows property controls the number left on their own at the start of a fragment.

The `orphans` and `widows` properties take an integer as a value, which represents the number of lines to keep together at the end and start of a fragment, respectively. Note that these properties only work inside a block container, such as a paragraph. If the block has fewer lines in it than the number that you specify as a value, all lines will be kept together.

In the example below, we are using the `orphans` property to control the number of lines left at the bottom of a column. You can change that value to see the effect on the breaking of the content.

## When things don’t work as expected

If you have small amounts of content and are trying to control breaks in a number of ways or on several elements, your content needs to break somewhere, so you may not always get the result you intended. To some extent your use of fragmentation is always a suggestion to the browser, to control breaks in this way if it is possible.

In addition to the above, browser support for these properties is a little patchy. The compatibility data charts on the individual property pages here on MDN can help you see which browsers support which features. In most cases, the fallback to breaks not being controlled is something you can live with, with suboptimal breaking being untidy rather than a disaster to your layout.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Columns/Handling_content_breaks_in_multicol" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Columns/Handling_content_breaks_in_multicol</a>
