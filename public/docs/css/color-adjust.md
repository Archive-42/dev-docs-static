# color-adjust

The `color-adjust` CSS property sets what, if anything, the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) may do to optimize the appearance of the element on the output device. By default, the browser is allowed to make any adjustments to the element's appearance it determines to be necessary and prudent given the type and capabilities of the output device.

## Syntax

    color-adjust: economy;
    color-adjust: exact;

The `color-adjust` property's value must be one of the following keywords.

### Values

`economy`  
The user agent is allowed to make adjustments to the element as it deems appropriate and prudent in order to optimize the output for the device it's being rendered for. For example, when printing, a browser might opt to leave out all background images and to adjust text colors to be sure the contrast is optimized for reading on white paper. This is the default.

`exact`  
The element's content has been specifically and carefully crafted to use colors, images, and styles in a thoughtful and/or important way, such that being altered by the browser might actually make things worse rather than better. The appearance of the content should not be changed except by the user's request. For example, a page might include a list of information with rows whose background colors alternate between white and a light grey. Removing the background color would decrease the legibility of the content.

## Usage notes

There are a number of reasons a browser might wish to deviate from the specified appearance, such as:

- The content uses text and background colors that will be too similar on the output device for legibility purposes.
- If the output device is a printer, and to save ink, dark or extremely dense background images might be removed.
- When printing a page, the browser might want to replace light-colored text on a dark background with dark text on a white background.

Any options the user agent offers the user to allow them to control the use of color and images will take priority over the value of `color-adjust`. In other words, there isn't any guarantee that `color-adjust` will do anything. Not only can the user override the behavior, but each user agent is allowed to decide for itself how to handle `color-adjust` in any given situation.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>economy</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    economy | exact

## Examples

### Preserving low contrast

In this example, a box is shown which uses a [`background-image`](background-image) and a translucent [`linear-gradient()`](<linear-gradient()>) function atop a black background color to have a dark blue gradient behind medium red text. For whatever reason, this is the desired appearance in any rendering environment, including on paper, so we also use `color-adjust: exact` to tell the browser not to make color or style adjustments to the box when rendering it.

#### CSS

    .my-box {
      background-color: black;
      background-image: linear-gradient(rgba(0, 0, 180, 0.5), rgba(70, 140, 220, 0.5));
      color: #900;
      width: 15rem;
      height: 6rem;
      text-align: center;
      font: 24px "Helvetica", sans-serif;
      display: flex;
      align-items: center;
      justify-content: center;
      color-adjust: exact;
    }

#### HTML

    <div class="my-box">
      <p>Need more contrast!</p>
    </div>

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-color-adjust-1/#propdef-color-adjust">CSS Color Adjustment Module Level 1<br />
<span class="small">The definition of 'color-adjust' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`color-adjust`

49

79

48

No

15

6

49

49

48

36

6

5.0

## See also

- [Applying color to HTML elements using CSS](https://developer.mozilla.org/en-US/docs/Web/HTML/Applying_color)
- Other color-related properties: [`color`](color), [`background-color`](background-color), [`border-color`](border-color), [`outline-color`](outline-color), [`text-decoration-color`](text-decoration-color), [`text-emphasis-color`](text-emphasis-color), [`text-shadow`](text-shadow), [`caret-color`](caret-color), and [`column-rule-color`](column-rule-color)
- [`background-image`](background-image)
- [`-webkit-print-color-adjust`](-webkit-print-color-adjust)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/color-adjust" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/color-adjust</a>
