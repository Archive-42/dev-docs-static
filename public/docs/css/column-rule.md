# column-rule

The `column-rule` [shorthand](shorthand_properties) [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the width, style, and color of the line drawn between columns in a multi-column layout.

It is a [shorthand property](shorthand_properties) that sets the individual `column-rule-*` properties in a single, convenient declaration: [`column-rule-width`](column-rule-width), [`column-rule-style`](column-rule-style), and [`column-rule-color`](column-rule-color).

**Note:** As with all shorthand properties, any individual value that is not specified is set to its corresponding initial value (possibly overriding values previously set using non-shorthand properties).

## Syntax

    column-rule: dotted;
    column-rule: solid 8px;
    column-rule: solid blue;
    column-rule: thick inset blue;

    /* Global values */
    column-rule: inherit;
    column-rule: initial;
    column-rule: unset;

The `column-rule` property is specified as one, two, or three of the values listed below, in any order.

### Values

`<'column-rule-width'>`  
Is a [`<length>`](length) or one of the three keywords, `thin`, `medium`, or `thick`. See [`border-width`](border-width) for details.

`<'column-rule-style'>`  
See [`border-style`](border-style) for possible values and details.

`<'column-rule-color'>`  
Is a [`<color>`](color_value) value.

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="column-rule-width"><code>column-rule-width</code></a>: <code>medium</code></li><li><a href="column-rule-style"><code>column-rule-style</code></a>: <code>none</code></li><li><a href="column-rule-color"><code>column-rule-color</code></a>: <code>currentcolor</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>multicol elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="column-rule-color"><code>column-rule-color</code></a>: computed color</li><li><a href="column-rule-style"><code>column-rule-style</code></a>: as specified</li><li><a href="column-rule-width"><code>column-rule-width</code></a>: the absolute length; <code>0</code> if the <a href="column-rule-style"><code>column-rule-style</code></a> is <code>none</code> or <code>hidden</code></li></ul></td></tr><tr class="odd"><td>Animation type</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="column-rule-color"><code>column-rule-color</code></a>: a <a href="color_value#interpolation">color</a></li><li><a href="column-rule-style"><code>column-rule-style</code></a>: discrete</li><li><a href="column-rule-width"><code>column-rule-width</code></a>: a <a href="length#interpolation">length</a></li></ul></td></tr></tbody></table>

## Formal syntax

    <'column-rule-width'> || <'column-rule-style'> || <'column-rule-color'>

## Examples

### Example 1

    /* Same as "medium dotted currentcolor" */
    p.foo { column-rule: dotted; }

    /* Same as "medium solid blue" */
    p.bar { column-rule: solid blue; }

    /* Same as "8px solid currentcolor" */
    p.baz { column-rule: solid 8px; }

    p.abc { column-rule: thick inset blue; }

### Example 2

#### HTML

    <p class="content-box">
      This is a bunch of text split into three columns.
      Take note of how the `column-rule` property is used
      to adjust the style, width, and color of the rule
      that appears between the columns.
    </p>

#### CSS

    .content-box {
      padding: 0.3em;
      background: #ff7;
      column-count: 3;
      column-rule: inset 2px #33f;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-multicol-1/#column-rule">CSS Multi-column Layout Module<br />
<span class="small">The definition of 'column-rule' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`column-rule`

50

1

12

12

52

3.5-74

Before Firefox 3, the default value for the `normal` keyword was `0` and not `1em`.

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
- [`column-rule-width`](column-rule-width)
- [`column-rule-color`](column-rule-color)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule</a>
