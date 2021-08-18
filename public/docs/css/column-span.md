# column-span

The `column-span` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property makes it possible for an element to span across all columns when its value is set to `all`.

    /* Keyword values */
    column-span: none;
    column-span: all;

    /* Global values */
    column-span: inherit;
    column-span: initial;
    column-span: unset;

An element that spans more than one column is called a **spanning element**.

## Syntax

The `column-span` property is specified as one of the keyword values listed below.

### Values

`none`  
The element does not span multiple columns.

`all`  
The element spans across all columns. Content in the normal flow that appears before the element is automatically balanced across all columns before the element appears. The element establishes a new block formatting context.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>in-flow block-level elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    none | all

## Examples

### Making a heading span columns

In this example, the heading is made to span across all the columns of the article.

#### HTML

    <article>
      <h2>Header spanning all of the columns</h2>
      <p>
         The h2 should span all the columns. The rest
         of the text should be distributed among the columns.
      </p>
      <p>This is a bunch of text split into three columns using the CSS `columns` property. The text is equally distributed over the columns.</p>
      <p>This is a bunch of text split into three columns using the CSS `columns` property. The text is equally distributed over the columns.</p>
      <p>This is a bunch of text split into three columns using the CSS `columns` property. The text is equally distributed over the columns.</p>
      <p>This is a bunch of text split into three columns using the CSS `columns` property. The text is equally distributed over the columns.</p>
    </article>

#### CSS

    article {
      columns: 3;
    }

    h2 {
      column-span: all;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-multicol-1/#column-span">CSS Multi-column Layout Module<br />
<span class="small">The definition of 'column-span' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`column-span`

50

6

12

12

71

65

10

11.1

15

9

5.1

50

≤37

50

18

65

11.1

14

9

5

5.0

1.0

## See also

- [Inline elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements)
- [`HTMLSpanElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/column-span" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/column-span</a>
