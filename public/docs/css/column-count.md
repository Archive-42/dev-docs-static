# column-count

The `column-count` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property breaks an element's content into the specified number of columns.

## Syntax

    /* Keyword value */
    column-count: auto;

    /* <integer> value */
    column-count: 3;

    /* Global values */
    column-count: inherit;
    column-count: initial;
    column-count: unset;

### Values

`auto`  
The number of columns is determined by other CSS properties, such as [`column-width`](column-width).

[`<integer>`](integer)  
Is a strictly positive [`<integer>`](integer) describing the ideal number of columns into which the content of the element will be flowed. If the [`column-width`](column-width) is also set to a non-`auto` value, it merely indicates the maximum allowed number of columns.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>Block containers except table wrapper boxes</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>an <a href="integer#interpolation">integer</a></td></tr></tbody></table>

## Formal syntax

    <integer> | auto

## Examples

### Splitting a paragraph across three columns

#### HTML

    <p class="content-box">
      This is a bunch of text split into three columns
      using the CSS `column-count` property. The text
      is equally distributed over the columns.
    </p>

#### CSS

    .content-box {
      column-count: 3;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-multicol-1/#cc">CSS Multi-column Layout Module<br />
<span class="small">The definition of 'column-count' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`column-count`

50

1

12

12

52

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

52

4

Prior to version 37, multiple columns didn't work with `display: table-caption` elements.

11.1

14

9

1

5.0

1.0

## See also

- [Multiple-column Layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout) (Learn Layout)
- [Basic Concepts of Multicol](css_columns/basic_concepts_of_multicol)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/column-count" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/column-count</a>
