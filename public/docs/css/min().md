# min()

The `min()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](css_functions) lets you set the smallest (most negative) value from a list of comma-separated expressions as the value of a CSS property value. The `min()` function can be used anywhere a [`<length>`](length), [`<frequency>`](frequency), [`<angle>`](angle), [`<time>`](time), [`<percentage>`](percentage), [`<number>`](number), or [`<integer>`](integer) is allowed.

In the first above example, the width will be at most 200px, but will be smaller if the viewport is less than 400px wide (in which case 1vw would be 4px, so 50vw would be 200px). In other words, the maximum width is 200px. Think of the `min()` value as providing the _maximum_ value a property can have.

## Syntax

The `min()` function takes one or more comma-separated expressions as its parameter, with the smallest (most negative) expression value result used as the value.

The expressions can be math expressions (using arithmetic operators), literal values, or other expressions, such as [`attr()`](<attr()>), that evaluate to a valid argument type (like [`<length>`](length)).

You can use different units for each value in your expression, if you wish. You may also use parentheses to establish computation order when needed.

### Notes

- Math expressions involving percentages for widths and heights on table columns, table column groups, table rows, table row groups, and table cells in both auto and fixed layout tables _may_ be treated as if `auto` had been specified.
- It is permitted to nest `max()` and other `min()` functions as expression values. The expressions are full math expressions, so you can use direct addition, subtraction, multiplication and division without using the `calc()` function itself.
- The expression can be values combining the addition ( + ), subtraction ( - ), multiplication ( \* ) and division ( / ) operators, using standard operator precedence rules. Make sure to put a space on each side of the + and - operands. The operands in the expression may be any `<length>` syntax value.
- You can (and often need to) combine `min()` and `max()` values, or use `min()` within a `clamp()` or `calc()` function.
- You can provide more than two arguments, if you have multiple constraints to apply.

### Formal syntax

    min( <calc-sum># )where
    <calc-sum> = <calc-product> [ [ '+' | '-' ] <calc-product> ]*where
    <calc-product> = <calc-value> [ '*' <calc-value> | '/' <number> ]*where
    <calc-value> = <number> | <dimension> | <percentage> | ( <calc-sum> )

## Accessibility concerns

When using `min()` to set a maximum font size, ensure that the font can still be scaled at least 200% for readability (without assistive technology like a zoom function).

- [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.4 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-scale.html)

## Examples

### Setting a maximum size for a label and input

Another use case for CSS functions is to set a maximum size on responsive form controls: enabling the width of labels and inputs to shrink as the width of the form shrinks.

Let's look at some CSS:

    input, label {
      padding: 2px;
      box-sizing: border-box;
      display: inline-block;
      width: min(40%, 400px);
      background-color: pink;
    }

    form {
      margin: 4px;
      border: 1px solid black;
      padding: 4px;
    }

Here, the form itself, along with the margin, border, and padding, will be 100% of its parent's width. We declare the input and label to be the lesser of 40% of the form width up to the padding or 400px wide, whichever is smaller. In other words, the widest that the label and input can be is 400px. The narrowest they will be is 40% of the form's width, which on a smartwatch's screen is very small.

    <form>
      <label>Type something:</label>
      <input type="text">
    </form>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-values-4/#calc-notation">CSS Values and Units Module Level 4<br />
<span class="small">The definition of 'min()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`min()`

79

79

75

No

66

11.1

79

79

79

57

11.3

12.0

## See also

- [`calc()`](<calc()>)
- [`clamp()`](<clamp()>)
- [`max()`](<max()>)
- [CSS Values](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/min()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/min()</a>
