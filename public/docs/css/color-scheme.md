# color-scheme

The `color-scheme` CSS property allows an element to indicate which color schemes it can comfortably be rendered in.

Common choices for operating system color schemes are "light" and "dark", or "day mode" and "night mode". When a user selects one of these color schemes, the operating system makes adjustments to the user interface. This includes form controls, scrollbars, and the used values of CSS system colors.

## Syntax

    color-scheme: normal;
    color-scheme: light;
    color-scheme: dark;
    color-scheme: light dark;

The `color-scheme` property's value must be one of the following keywords.

### Values

`normal`  
Indicates that the element isn't aware of any color schemes, and so should be rendered using the browser's default color scheme.

`light`  
Indicates that the element can be rendered using the operating system light color scheme.

`dark`  
Indicates that the element can be rendered using the operating system dark color scheme.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>all elements and text</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    normal | [ light | dark | <custom-ident> ]+

## Examples

### Adapting to color schemes

To opt the entire page into the user's color scheme preferences declare `color-scheme` on the [`:root`](:root) element.

    :root {
      color-scheme: light dark;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-color-adjust-1/#color-scheme-prop">CSS Color Adjustment Module Level 1<br />
<span class="small">The definition of 'color-scheme' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`color-scheme`

81

81

No

No

68

13

81

81

No

58

13

No

`only_dark`

No

No

No

No

No

13

No

No

No

No

13

No

`only_light`

81-85

81-85

No

No

68-71

13

No

81-85

No

58-60

13

No

## See also

- [Applying color to HTML elements using CSS](https://developer.mozilla.org/en-US/docs/Web/HTML/Applying_color)
- Other color-related properties: [`color`](color), [`background-color`](background-color), [`border-color`](border-color), [`outline-color`](outline-color), [`text-decoration-color`](text-decoration-color), [`text-emphasis-color`](text-emphasis-color), [`text-shadow`](text-shadow), [`caret-color`](caret-color), and [`column-rule-color`](column-rule-color)
- [`background-image`](background-image)
- [`-webkit-print-color-adjust`](-webkit-print-color-adjust)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/color-scheme" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/color-scheme</a>
