# column-rule-width

The `column-rule-width` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the width of the line drawn between columns in a multi-column layout.

## Syntax

    /* Keyword values */
    column-rule-width: thin;
    column-rule-width: medium;
    column-rule-width: thick;

    /* <length> values */
    column-rule-width: 1px;
    column-rule-width: 2.5em;

    /* Global values */
    column-rule-width: inherit;
    column-rule-width: initial;
    column-rule-width: unset;

The `column-rule-width` property is specified as a single `<'border-width'>` value.

### Values

`<'border-width'>`  
Is a keyword defined by [`border-width`](border-width) describing the width of the rule. It may be either a [`<length>`](length) or one of the `thin`, `medium`, or `thick` keywords.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>medium</code></td></tr><tr class="even"><td>Applies to</td><td>multicol elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>the absolute length; <code>0</code> if the <a href="column-rule-style"><code>column-rule-style</code></a> is <code>none</code> or <code>hidden</code></td></tr><tr class="odd"><td>Animation type</td><td>a <a href="length#interpolation">length</a></td></tr></tbody></table>

## Formal syntax

    <'border-width'>

## Examples

### Setting a thick column rule

#### HTML

    <p>This is a bunch of text split into three columns.
       The `column-rule-width` property is used to change
       the width of the line that is drawn between columns.
       Don't you think that's wonderful?</p>

#### CSS

    p {
      column-count: 3;
      column-rule-style: solid;
      column-rule-width: thick;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-multicol-1/#crw">CSS Multi-column Layout Module<br />
<span class="small">The definition of 'column-rule-width' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`column-rule-width`

50

1

12

12

52

3.5-74

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

11.1

14

9

1

5.0

1.0

## See also

- [Multiple-column Layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout)
- [`column-rule-style`](column-rule-style)
- [`column-rule-color`](column-rule-color)
- [`column-rule`](column-rule)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-width" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-width</a>
