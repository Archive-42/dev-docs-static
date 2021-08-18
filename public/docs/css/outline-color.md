# outline-color

The `outline-color` CSS property sets the color of an element's outline.

## Syntax

    /* <color> values */
    outline-color: #f92525;
    outline-color: rgb(30,222,121);
    outline-color: blue;

    /* Keyword value */
    outline-color: invert;

    /* Global values */
    outline-color: inherit;
    outline-color: initial;
    outline-color: unset;

The `outline-color` property is specified as any one of the values listed below.

### Values

[`<color>`](color_value)  
The color of the outline, specified as a `<color>`.

`invert`  
To ensure the outline is visible, performs a color inversion of the background. Note that browsers are not required to support this value; if they don't, this keyword is considered invalid.

## Description

An outline is a line that is drawn around an element, outside the [`border`](border). Unlike the element's border, the outline is drawn outside the element's frame, and may overlap other content. The border, on the other hand, will actually alter the page's layout to ensure that it fits without overlapping anything else (unless you explicitly set it to overlap).

It is often more convenient to use the shorthand property [`outline`](outline) when defining the appearance of an outline.

## Accessibility concerns

Custom [focus styles](:focus) commonly involve making adjustments to the [`outline`](outline) property. If the color of the outline is adjusted, it is important to ensure that the contrast ratio between it and the background the outline is placed over is high enough that people experiencing low vision conditions will be able to perceive it.

Color contrast ratio is determined by comparing the luminosity of the text and background color values. In order to meet current [Web Content Accessibility Guidelines (WCAG)](https://www.w3.org/WAI/intro/wcag), a ratio of 4.5:1 is required for text content and 3:1 for larger text such as headings. Large text is defined as 18.66px and [bold](font-weight) or larger, or 24px or larger.

- [WebAIM: Color Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.3 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>invert</code>, for browsers supporting it, <code>currentColor</code> for the other</td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>For the keyword <code>invert</code>, the computed value is <code>invert</code>. For the color value, if the value is translucent, the computed value will be the <code>rgba()</code> corresponding one. If it isn't, it will be the <code>rgb()</code> corresponding one. The <code>transparent</code> keyword maps to <code>rgba(0,0,0,0)</code>.</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="color_value#interpolation">color</a></td></tr></tbody></table>

## Formal syntax

    <color> | invertwhere
    <color> = <rgb()> | <rgba()> | <hsl()> | <hsla()> | <hex-color> | <named-color> | currentcolor | <deprecated-system-color>where
    <rgb()> = rgb( <percentage>{3} [ / <alpha-value> ]? ) | rgb( <number>{3} [ / <alpha-value> ]? ) | rgb( <percentage>#{3} , <alpha-value>? ) | rgb( <number>#{3} , <alpha-value>? )
    <rgba()> = rgba( <percentage>{3} [ / <alpha-value> ]? ) | rgba( <number>{3} [ / <alpha-value> ]? ) | rgba( <percentage>#{3} , <alpha-value>? ) | rgba( <number>#{3} , <alpha-value>? )
    <hsl()> = hsl( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsl( <hue>, <percentage>, <percentage>, <alpha-value>? )
    <hsla()> = hsla( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsla( <hue>, <percentage>, <percentage>, <alpha-value>? )where
    <alpha-value> = <number> | <percentage>
    <hue> = <number> | <angle>

## Examples

### Setting a solid blue outline

#### HTML

    <p>My outline is blue, as you can see.</p>

#### CSS

    p {
      outline: 2px solid;      /* Set the outline width and style */
      outline-color: #0000FF;  /* Make the outline blue */
      margin: 5px;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-ui-3/#outline-color">CSS Basic User Interface Module Level 3<br />
<span class="small">The definition of 'outline-color' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/ui.html#propdef-outline-color">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'outline-color' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`outline-color`

1

12

1.5

1-3.6

8

7

1.2

37

18

4

14

1

1.0

`invert`

No

12-79

1-3

8

7-15

No

No

No

No

No

No

No

## See also

- [`outline`](outline)
- [`outline-color`](outline-color)
- [`outline-style`](outline-style)
- [`outline-width`](outline-width)
- The [`<color>`](color_value) data type
- Other color-related properties: [`color`](color), [`background-color`](background-color), [`border-color`](border-color), [`text-decoration-color`](text-decoration-color), [`text-emphasis-color`](text-emphasis-color), [`text-shadow`](text-shadow), [`caret-color`](caret-color), and [`column-rule-color`](column-rule-color)
- [Applying color to HTML elements using CSS](https://developer.mozilla.org/en-US/docs/Web/HTML/Applying_color)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/outline-color" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/outline-color</a>
