# column-rule-style

The `column-rule-style` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the style of the line drawn between columns in a multi-column layout.

## Syntax

    /* <'border-style'> values */
    column-rule-style: none;
    column-rule-style: hidden;
    column-rule-style: dotted;
    column-rule-style: dashed;
    column-rule-style: solid;
    column-rule-style: double;
    column-rule-style: groove;
    column-rule-style: ridge;
    column-rule-style: inset;
    column-rule-style: outset;

    /* Global values */
    column-rule-style: inherit;
    column-rule-style: initial;
    column-rule-style: unset;

The `column-rule-style` property is specified as a single `<'border-style'>` value.

### Values

`<'border-style'>`  
Is a keyword defined by [`border-style`](border-style) describing the style of the rule. The styling must be interpreted as in the collapsing border model.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>multicol elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <'border-style'>

## Examples

### Setting a dashed column rule

#### HTML

    <p>This is a bunch of text split into three columns.
       The `column-rule-style` property is used to change
       the style of the line that is drawn between columns.
       Don't you think that's wonderful?</p>

#### CSS

    p {
      column-count: 3;
      column-rule-style: dashed;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-multicol-1/#crs">CSS Multi-column Layout Module<br />
<span class="small">The definition of 'column-rule-style' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`column-rule-style`

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
- [`column-rule`](column-rule)
- [`column-rule-width`](column-rule-width)
- [`column-rule-color`](column-rule-color)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-style" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-style</a>
