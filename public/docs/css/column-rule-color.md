# column-rule-color

The `column-rule-color` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the color of the line drawn between columns in a multi-column layout.

## Syntax

    /* <color> values */
    column-rule-color: red;
    column-rule-color: rgb(192, 56, 78);
    column-rule-color: transparent;
    column-rule-color: hsla(0, 100%, 50%, 0.6);

    /* Global values */
    column-rule-color: inherit;
    column-rule-color: initial;
    column-rule-color: unset;

The `column-rule-color` property is specified as a single `<color>` value.

### Values

[`<color>`](color_value)  
The color of the rule that separates columns.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>currentcolor</code></td></tr><tr class="even"><td>Applies to</td><td>multicol elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>computed color</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="color_value#interpolation">color</a></td></tr></tbody></table>

## Formal syntax

    <color>where
    <color> = <rgb()> | <rgba()> | <hsl()> | <hsla()> | <hex-color> | <named-color> | currentcolor | <deprecated-system-color>where
    <rgb()> = rgb( <percentage>{3} [ / <alpha-value> ]? ) | rgb( <number>{3} [ / <alpha-value> ]? ) | rgb( <percentage>#{3} , <alpha-value>? ) | rgb( <number>#{3} , <alpha-value>? )
    <rgba()> = rgba( <percentage>{3} [ / <alpha-value> ]? ) | rgba( <number>{3} [ / <alpha-value> ]? ) | rgba( <percentage>#{3} , <alpha-value>? ) | rgba( <number>#{3} , <alpha-value>? )
    <hsl()> = hsl( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsl( <hue>, <percentage>, <percentage>, <alpha-value>? )
    <hsla()> = hsla( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsla( <hue>, <percentage>, <percentage>, <alpha-value>? )where
    <alpha-value> = <number> | <percentage>
    <hue> = <number> | <angle>

## Examples

### Setting a blue column rule

#### HTML

    <p>This is a bunch of text split into three columns.
       The `column-rule-color` property is used to change
       the color of the line that is drawn between columns.
       Don't you think that's wonderful?</p>

#### CSS

    p {
      column-count: 3;
      column-rule-style: solid;
      column-rule-color: blue;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-multicol-1/#crc">CSS Multi-column Layout Module<br />
<span class="small">The definition of 'column-rule-color' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`column-rule-color`

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

- The [`<color>`](color_value) data type
- Other color-related properties: [`color`](color), [`background-color`](background-color), [`border-color`](border-color), [`outline-color`](outline-color), [`text-decoration-color`](text-decoration-color), [`text-emphasis-color`](text-emphasis-color), [`text-shadow`](text-shadow), and [`caret-color`](caret-color)
- [Applying color to HTML elements using CSS](https://developer.mozilla.org/en-US/docs/Web/HTML/Applying_color)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-color" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-color</a>
