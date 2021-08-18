# column-width

The `column-width` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the ideal column width in a multi-column layout. The container will have as many columns as can fit without any of them having a width less than the `column-width` value. If the width of the container is narrower than the specified value, the single column's width will be smaller than the declared column width.

This property can help you create responsive designs that fit different screen sizes. Especially in the presence of the [`column-count`](column-count) property (which has precedence), you must specify all related length values to achieve an exact column width. In horizontal text these are [`width`](width), [`column-width`](column-width), [`column-gap`](column-gap), and [`column-rule-width`](column-rule-width).

## Syntax

    /* Keyword value */
    column-width: auto;

    /* <length> values */
    column-width: 60px;
    column-width: 15.5em;
    column-width: 3.3vw;

    /* Global values */
    column-width: inherit;
    column-width: initial;
    column-width: unset;

The `column-width` property is specified as one of the values listed below.

### Values

[`<length>`](length)  
Indicates the optimal column width. The actual column width may differ from the specified value: it may be wider when necessary to fill available space, and narrower when the available space is too small. The value must be strictly positive or the declaration is invalid. Percentage values are also invalid.

`auto`  
The width of the column is determined by other CSS properties, such as [`column-count`](column-count).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>Block containers except table wrapper boxes</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>the absolute length, zero or larger</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="length#interpolation">length</a></td></tr></tbody></table>

## Formal syntax

    <length> | auto

## Examples

### Setting column width in pixels

#### HTML

    <p class="content-box">
    Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.
    </p>

#### CSS

    .content-box {
      column-width: 100px;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-sizing-3/#column-sizing">CSS Box Sizing Module Level 3<br />
<span class="small">The definition of 'column-width' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds intrinsic sizes via the keywords <code>min-content</code>, <code>max-content</code>, and <code>fit-content</code>.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-multicol-1/#cw">CSS Multi-column Layout Module<br />
<span class="small">The definition of 'column-width' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`column-width`

50

1

12

12

50

1.5-74

Prior to version 37, multiple columns didn't work with `display: table-caption` elements.

10

11.1

15

9

3

50

≤37

50

18

50

4

Prior to version 37, multiple columns didn't work with `display: table-caption` elements.

11.1

15

9

1

5.0

1.0

`intrinsic_sizes`

No

See [bug 964183](https://crbug.com/964183)

No

No

No

No

No

No

No

No

No

No

No

## See also

- [Multiple-column Layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout) (Learn Layout)
- [Basic Concepts of Multicol](css_columns/basic_concepts_of_multicol)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/column-width" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/column-width</a>
