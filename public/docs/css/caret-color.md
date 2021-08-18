# caret-color

The `caret-color` CSS property sets the color of the **insertion caret**, the visible marker where the next character typed will be inserted. This is sometimes referred to as the **text input cursor**. The caret appears in elements such as [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) or those with the [`contenteditable`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-contenteditable) attribute. The caret is typically a thin vertical line that flashes to help make it more noticeable. By default, it is black, but its color can be altered with this property.

Note that the insertion caret is only one type of caret. For example, many browsers have a “navigation caret,” which acts similarly to an insertion caret but can be moved around in non-editable text. On the other hand, the mouse cursor image shown when hovering over text where the [`cursor`](cursor) property is `auto`, or when hovering over an element where the `cursor` property is `text` or `vertical-text`, though it sometimes looks like a caret, is not a caret (it’s a cursor).

## Syntax

    /* Keyword values */
    caret-color: auto;
    caret-color: transparent;
    caret-color: currentcolor;

    /* <color> values */
    caret-color: red;
    caret-color: #5729e9;
    caret-color: rgb(0, 200, 0);
    caret-color: hsla(228, 4%, 24%, 0.8);

### Values

`auto`  
The user agent selects an appropriate color for the caret. This is generally [`currentcolor`](color_value#currentcolor_keyword), but the user agent may choose a different color to ensure good visibility and contrast with the surrounding content, taking into account the value of `currentcolor`, the background, shadows, and other factors.

**Note:** While user agents may use `currentcolor` (which is usually animatable) for the `auto` value, `auto` is not interpolated in transitions and animations.

[`<color>`](color_value)  
The color of the caret.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td><code>auto</code> is computed as specified and <code>&lt;color&gt;</code> values are computed as defined for the <a href="color"><code>color</code></a> property.</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="color_value#interpolation">color</a></td></tr></tbody></table>

## Formal syntax

    auto | <color>where
    <color> = <rgb()> | <rgba()> | <hsl()> | <hsla()> | <hex-color> | <named-color> | currentcolor | <deprecated-system-color>where
    <rgb()> = rgb( <percentage>{3} [ / <alpha-value> ]? ) | rgb( <number>{3} [ / <alpha-value> ]? ) | rgb( <percentage>#{3} , <alpha-value>? ) | rgb( <number>#{3} , <alpha-value>? )
    <rgba()> = rgba( <percentage>{3} [ / <alpha-value> ]? ) | rgba( <number>{3} [ / <alpha-value> ]? ) | rgba( <percentage>#{3} , <alpha-value>? ) | rgba( <number>#{3} , <alpha-value>? )
    <hsl()> = hsl( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsl( <hue>, <percentage>, <percentage>, <alpha-value>? )
    <hsla()> = hsla( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsla( <hue>, <percentage>, <percentage>, <alpha-value>? )where
    <alpha-value> = <number> | <percentage>
    <hue> = <number> | <angle>

## Examples

### Setting a custom caret color

#### HTML

    <input value="This field uses a default caret." size="64"/>
    <input class="custom" value="I have a custom caret color!" size="64"/>
    <p contenteditable class="custom">This paragraph can be
       edited, and its caret has a custom color as well!</p>

#### CSS

    input {
      caret-color: auto;
      display: block;
      margin-bottom: .5em;
    }

    input.custom {
      caret-color: red;
    }

    p.custom {
      caret-color: green;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-ui-3/#propdef-caret-color">CSS Basic User Interface Module Level 3<br />
<span class="small">The definition of 'caret-color' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`caret-color`

57

79

53

No

44

11.1

57

57

53

43

11.3

While the property is recognized, implementation is incomplete. The color of the caret does not always match the color set for the element in focus. See [bug 177489](https://webkit.org/b/177489).

7.0

## See also

- The [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element
- The HTML [`contenteditable`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-contenteditable) attribute, which can be used to make any element's text editable
- [Making content editable](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Editable_content)
- [Applying color to HTML elements using CSS](https://developer.mozilla.org/en-US/docs/Web/HTML/Applying_color)
- The [`<color>`](color_value) data type
- Other color-related properties: [`color`](color), [`background-color`](background-color), [`border-color`](border-color), [`outline-color`](outline-color), [`text-decoration-color`](text-decoration-color), [`text-emphasis-color`](text-emphasis-color), [`text-shadow`](text-shadow), [`caret-color`](caret-color), and [`column-rule-color`](column-rule-color)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/caret-color" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/caret-color</a>
