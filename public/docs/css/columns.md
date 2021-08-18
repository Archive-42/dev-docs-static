# columns

The `columns` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) shorthand property sets the number of columns to use when drawing an element's contents, as well as those columns' widths.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`column-count`](column-count)
- [`column-width`](column-width)

## Syntax

    /* Column width */
    columns: 18em;

    /* Column count */
    columns: auto;
    columns: 2;

    /* Both column width and count */
    columns: 2 auto;
    columns: auto 12em;
    columns: auto auto;

    /* Global values */
    columns: inherit;
    columns: initial;
    columns: unset;

The `columns` property may be specified as one or two of the values listed below, in any order.

### Values

`<'column-width'>`  
The ideal column width, defined as a [`<length>`](length) or the keyword `auto`. The actual width may be wider or narrower to fit the available space. See [`column-width`](column-width).

`<'column-count'>`  
The ideal number of columns into which the element's content should be flowed, defined as an [`<integer>`](integer) or the keyword `auto`. If neither this value nor the column's width are `auto`, it merely indicates the maximum allowable number of columns. See [`column-count`](column-count).

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="column-width"><code>column-width</code></a>: <code>auto</code></li><li><a href="column-count"><code>column-count</code></a>: <code>auto</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>Block containers except table wrapper boxes</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="column-width"><code>column-width</code></a>: the absolute length, zero or larger</li><li><a href="column-count"><code>column-count</code></a>: as specified</li></ul></td></tr><tr class="odd"><td>Animation type</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="column-width"><code>column-width</code></a>: a <a href="length#interpolation">length</a></li><li><a href="column-count"><code>column-count</code></a>: an <a href="integer#interpolation">integer</a></li></ul></td></tr></tbody></table>

## Formal syntax

    <'column-width'> || <'column-count'>

## Examples

### Setting three equal columns

#### HTML

    <p class="content-box">
      This is a bunch of text split into three columns
      using the CSS `columns` property. The text
      is equally distributed over the columns.
    </p>

#### CSS

    .content-box {
      columns: 3 auto;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-multicol-1/#columns">CSS Multi-column Layout Module<br />
<span class="small">The definition of 'columns' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`columns`

50

50

12

12

52

9-74

Prior to version 37, multiple columns didn't work with `display: table-caption` elements.

10

11.1

15

9

3

50

2

50

52

22

Prior to version 37, multiple columns didn't work with `display: table-caption` elements.

11.1

14

9

3.2

5.0

## See also

- [`widows`](widows)
- [`orphans`](orphans)
- [Paged media](https://developer.mozilla.org/en-US/docs/Web/CSS/Paged_Media)
- [Multiple-column Layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/columns" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/columns</a>
