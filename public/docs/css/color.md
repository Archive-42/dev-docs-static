# color

The `color` CSS property sets the foreground [color value](color_value) of an element's text and [text decorations](text-decoration), and sets the [`<currentcolor>`](color_value#currentcolor_keyword) value. `currentcolor` may be used as an indirect value on _other_ properties and is the default for other color properties, such as [`border-color`](border-color).

For an overview of using color in HTML, see [Applying color to HTML elements using CSS](https://developer.mozilla.org/en-US/docs/Web/HTML/Applying_color).

## Syntax

    /* Keyword values */
    color: currentcolor;

    /* <named-color> values */
    color: red;
    color: orange;
    color: tan;
    color: rebeccapurple;

    /* <hex-color> values */
    color: #090;
    color: #009900;
    color: #090a;
    color: #009900aa;

    /* <rgb()> values */
    color: rgb(34, 12, 64, 0.6);
    color: rgba(34, 12, 64, 0.6);
    color: rgb(34 12 64 / 0.6);
    color: rgba(34 12 64 / 0.3);
    color: rgb(34.0 12 64 / 60%);
    color: rgba(34.6 12 64 / 30%);

    /* <hsl()> values */
    color: hsl(30, 100%, 50%, 0.6);
    color: hsla(30, 100%, 50%, 0.6);
    color: hsl(30 100% 50% / 0.6);
    color: hsla(30 100% 50% / 0.6);
    color: hsl(30.0 100% 50% / 60%);
    color: hsla(30.2 100% 50% / 60%);

    /* Global values */
    color: inherit;
    color: initial;
    color: unset;

The `color` property is specified as a single [`<color>`](color_value) value.

Note that the value must be a uniform [`color`](color). It can't be a [`<gradient>`](gradient), which is actually a type of [`<image>`](image).

### Values

[`<color>`](color_value)  
Sets the color of the textual and decorative parts of the element.

## Accessibility concerns

It is important to ensure that the contrast ratio between the color of the text and the background the text is placed over is high enough that people experiencing low vision conditions will be able to read the content of the page.

Color contrast ratio is determined by comparing the luminosity of the text and background color values. In order to meet current [Web Content Accessibility Guidelines (WCAG)](https://www.w3.org/WAI/intro/wcag), a ratio of 4.5:1 is required for text content and 3:1 for larger text such as headings. Large text is defined as 18.66px and [bold](font-weight) or larger, or 24px or larger.

- [WebAIM: Color Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.3 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>Varies from one browser to another</td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>If the value is translucent, the computed value will be the <code>rgba()</code> corresponding one. If it isn't, it will be the <code>rgb()</code> corresponding one. The <code>transparent</code> keyword maps to <code>rgba(0,0,0,0)</code>.</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="color_value#interpolation">color</a></td></tr></tbody></table>

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

### Making text red

The following are all ways to make a paragraph's text red:

    p { color: red; }
    p { color: #f00; }
    p { color: #ff0000; }
    p { color: rgb(255,0,0); }
    p { color: rgb(100%, 0%, 0%); }
    p { color: hsl(0, 100%, 50%); }

    /* 50% translucent */
    p { color: #ff000080; }
    p { color: rgba(255, 0, 0, 0.5); }
    p { color: hsla(0, 100%, 50%, 0.5); }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-color/#the-color-property">CSS Color Module Level 4<br />
<span class="small">The definition of 'color' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds commaless syntaxes for the <code>rgb()</code>, <code>rgba()</code>, <code>hsl()</code>, and <code>hsla()</code> functions. Allows alpha values in <code>rgb()</code> and <code>hsl()</code>, turning <code>rgba()</code> and <code>hsla()</code> into (deprecated) aliases for them.<br />
Adds color keyword <code>rebeccapurple</code>.<br />
Adds 4- and 8-digit hex color values, where the last digit(s) represents the alpha value.<br />
Adds <code>hwb()</code>, <code>device-cmyk()</code>, and <code>color()</code> functions.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-color-3/#color">CSS Color Module Level 3<br />
<span class="small">The definition of 'color' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Deprecates system-colors. Adds SVG colors. Adds the <code>rgba()</code>, <code>hsl()</code>, and <code>hsla()</code> functions.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/colors.html#colors">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'color' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Adds the <code>orange</code> color and the system colors.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#color">CSS Level 1<br />
<span class="small">The definition of 'color' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`color`

1

12

1

3

3.5

1

1

18

4

10.1

1

1.0

## See also

- The [`<color>`](color_value) data type
- Other color-related properties: [`background-color`](background-color), [`border-color`](border-color), [`outline-color`](outline-color), [`text-decoration-color`](text-decoration-color), [`text-emphasis-color`](text-emphasis-color), [`text-shadow`](text-shadow), [`caret-color`](caret-color), [`column-rule-color`](column-rule-color), and [`color-adjust`](color-adjust)
- [Applying color to HTML elements using CSS](https://developer.mozilla.org/en-US/docs/Web/HTML/Applying_color)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/color" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/color</a>
