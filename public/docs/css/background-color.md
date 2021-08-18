# background-color

The `background-color` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the background color of an element.

## Syntax

    /* Keyword values */
    background-color: red;
    background-color: indigo;

    /* Hexadecimal value */
    background-color: #bbff00;    /* Fully opaque */
    background-color: #bf0;       /* Fully opaque shorthand */
    background-color: #11ffee00;  /* Fully transparent */
    background-color: #1fe0;      /* Fully transparent shorthand  */
    background-color: #11ffeeff;  /* Fully opaque */
    background-color: #1fef;      /* Fully opaque shorthand  */

    /* RGB value */
    background-color: rgb(255, 255, 128);        /* Fully opaque */
    background-color: rgba(117, 190, 218, 0.5);  /* 50% transparent */

    /* HSL value */
    background-color: hsl(50, 33%, 25%);         /* Fully opaque */
    background-color: hsla(50, 33%, 25%, 0.75);  /* 75% opaque, i.e. 25% transparent */

    /* Special keyword values */
    background-color: currentcolor;
    background-color: transparent;

    /* Global values */
    background-color: currentcolor;
    background-color: transparent;
    background-color: transparent;

The `background-color` property is specified as a single `<color>` value.

### Values

[`<color>`](color_value)  
The uniform color of the background. It is rendered behind any [`background-image`](background-image) that is specified, although the color will still be visible through any transparency in the image.

## Accessibility concerns

It is important to ensure that the contrast ratio between the background color and the color of the text placed over it is high enough that people experiencing low vision conditions will be able to read the content of the page.

Color contrast ratio is determined by comparing the luminance of the text and background color values. In order to meet current [Web Content Accessibility Guidelines (WCAG)](https://www.w3.org/WAI/intro/wcag), a ratio of 4.5:1 is required for text content and 3:1 for larger text such as headings. Large text is defined as 18.66px and [bold](font-weight) or larger, or 24px or larger.

- [WebAIM: Color Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.3 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>transparent</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>computed color</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="color_value#interpolation">color</a></td></tr></tbody></table>

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

### HTML

    <div class="exampleone">
      Lorem ipsum dolor sit amet, consectetuer
    </div>

    <div class="exampletwo">
      Lorem ipsum dolor sit amet, consectetuer
    </div>

    <div class="examplethree">
      Lorem ipsum dolor sit amet, consectetuer
    </div>

### CSS

    .exampleone { background-color: transparent; }

    .exampletwo {
      background-color: rgb(153,102,153);
      color: rgb(255,255,204);
    }

    .examplethree {
      background-color: #777799;
      color: #FFFFFF;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Comment</th><th>Feedback</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#background-color">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'background-color' in that specification.</span></a></td><td>Though technically removing the <code>transparent</code> keyword, this doesn't change anything as it has been incorporated as a true <a href="color_value"><code>&lt;color&gt;</code></a></td><td><a href="https://github.com/w3c/csswg-drafts/labels/css-backgrounds-3">Backgrounds Level 3 GitHub issues</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/colors.html#propdef-background-color">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'background-color' in that specification.</span></a></td><td></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#background-color">CSS Level 1<br />
<span class="small">The definition of 'background-color' in that specification.</span></a></td><td>Initial definition</td><td></td></tr></tbody></table>

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

`background-color`

1

12

1

4

In Internet Explorer 8 and 9, there is a bug where a computed `background-color` of `transparent` causes `click` events to not get fired on overlaid elements.

3.5

1

≤37

18

4

14

1

1.0

## See also

- [Multiple backgrounds](css_backgrounds_and_borders/using_multiple_backgrounds)
- The [`<color>`](color_value) data type
- Other color-related properties: [`color`](color), [`border-color`](border-color), [`outline-color`](outline-color), [`text-decoration-color`](text-decoration-color), [`text-emphasis-color`](text-emphasis-color), [`text-shadow`](text-shadow), [`caret-color`](caret-color), and [`column-rule-color`](column-rule-color)
- [Applying color to HTML elements using CSS](https://developer.mozilla.org/en-US/docs/Web/HTML/Applying_color)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/background-color" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/background-color</a>
