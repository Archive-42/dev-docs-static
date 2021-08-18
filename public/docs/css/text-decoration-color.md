# text-decoration-color

The `text-decoration-color` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the color of decorations added to text by [`text-decoration-line`](text-decoration-line).

The color applies to decorations, such as underlines, overlines, strikethroughs, and wavy lines like those used to mark misspellings, in the scope of the property's value.

CSS does not provide a direct mechanism for specifying a unique color for each line type. This effect can nevertheless be achieved by nesting elements, applying a different line type to each element (with the [`text-decoration-line`](text-decoration-line) property), and specifying the line color (with `text-decoration-color`) on a per-element basis.

## Syntax

    /* <color> values */
    text-decoration-color: currentcolor;
    text-decoration-color: red;
    text-decoration-color: #00ff00;
    text-decoration-color: rgba(255, 128, 128, 0.5);
    text-decoration-color: transparent;

    /* Global values */
    text-decoration-color: inherit;
    text-decoration-color: initial;
    text-decoration-color: unset;

### Values

[`<color>`](color_value)  
The color of the line decoration.

## Accessibility concerns

It is important to ensure that the contrast ratio between the color of the text, the background the text is placed over, and the text decoration line is high enough that people experiencing low vision conditions will be able to read the content of the page. Color contrast ratio is determined by comparing the luminosity of the text and background color values.

Color alone should not be used to convey meaning. For example, change of text and text-decoration-color alone is not enough to indicate a link has focus.

- [WebAIM: Color Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.3 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>currentcolor</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>computed color</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="color_value#interpolation">color</a></td></tr></tbody></table>

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

### Basic example

    <p>This paragraph has <s>some erroneous text</s>
        inside it that I want to call attention to.</p>

    p {
      text-decoration-line: underline;
      text-decoration-color: cyan;
    }

    s {
      text-decoration-line: line-through;
      text-decoration-color: red;
      text-decoration-style: wavy;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-decor-3/#text-decoration-color-property">CSS Text Decoration Module Level 3<br />
<span class="small">The definition of 'text-decoration-color' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition. The <a href="text-decoration"><code>text-decoration</code></a> property is now a shorthand to define multiple related properties.</td></tr></tbody></table>

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

`text-decoration-color`

57

79

36

6-39

No

44

12.1

8

57

57

36

6-39

43

12.2

8

7.0

## See also

- When setting multiple line-decoration properties at once, it may be more convenient to use the [`text-decoration`](text-decoration) shorthand property instead.
- The [`<color>`](color_value) data type
- Other color-related properties: [`background-color`](background-color), [`border-color`](border-color), [`outline-color`](outline-color), [`text-decoration-color`](text-decoration-color), [`text-emphasis-color`](text-emphasis-color), [`text-shadow`](text-shadow), [`caret-color`](caret-color), and [`column-rule-color`](column-rule-color)
- [Applying color to HTML elements using CSS](https://developer.mozilla.org/en-US/docs/Web/HTML/Applying_color)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-color" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-color</a>
