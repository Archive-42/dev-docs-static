# text-emphasis-color

The `text-emphasis-color` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the color of emphasis marks. This value can also be set using the [`text-emphasis`](text-emphasis) shorthand.

    /* Initial value */
    text-emphasis-color: currentcolor;

    /* <color> */
    text-emphasis-color: #555;
    text-emphasis-color: blue;
    text-emphasis-color: rgba(90, 200, 160, 0.8);
    text-emphasis-color: transparent;

    /* Global values */
    text-emphasis-color: inherit;
    text-emphasis-color: initial;
    text-emphasis-color: unset;

## Syntax

### Values

`<color>`  
Defines the color of the emphasis marks. If no color is present, it defaults to `currentcolor`.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>currentcolor</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>computed color</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="color_value#interpolation">color</a></td></tr></tbody></table>

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

### Emphasis with a color and custom character

#### CSS

    em {
      text-emphasis-color: green;
      text-emphasis-style: "*";
    }

#### HTML

    <p>Here's an example:</p>

    <em>This has emphasis marks!</em>

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-decor-3/#text-emphasis-color-property">CSS Text Decoration Module Level 3<br />
<span class="small">The definition of 'text-emphasis' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`text-emphasis-color`

25

79

46

No

15

6.1

6.1

4.4

25

46

14

7

7

1.5

## See also

- The [`<color>`](color_value) data type
- The other emphasis mark related properties: [`text-emphasis-style`](text-emphasis-style), [`text-emphasis`](text-emphasis), and [`text-emphasis-position`](text-emphasis-position).
- Other color-related properties: [`color`](color), [`background-color`](background-color), [`border-color`](border-color), [`outline-color`](outline-color), [`text-emphasis-color`](text-emphasis-color), [`text-shadow`](text-shadow), [`caret-color`](caret-color), and [`column-rule-color`](column-rule-color)
- [Applying color to HTML elements using CSS](https://developer.mozilla.org/en-US/docs/Web/HTML/Applying_color)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-color" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-color</a>
