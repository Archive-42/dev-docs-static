# scrollbar-color

The `scrollbar-color` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the color of the scrollbar track and thumb.

The **track** refers to the background of the scrollbar, which is generally fixed regardless of the scrolling position.

The **thumb** refers to the moving part of the scrollbar, which usually floats on top of the track.

## Syntax

    /* Keyword values */
    scrollbar-color: auto;
    scrollbar-color: dark;
    scrollbar-color: light;

    /* <color> values */
    scrollbar-color: rebeccapurple green;   /* Two valid colors.
    The first applies to the thumb of the scrollbar, the second to the track. */

    /* Global values */
    scrollbar-color: inherit;
    scrollbar-color: initial;
    scrollbar-color: unset;

### Values

`<scrollbar-color>`  
Defines the color of the scrollbar.

<table><tbody><tr class="odd"><td><code>auto</code></td><td>Default platform rendering for the track portion of the scrollbar, in the absence of any other related scrollbar color properties.</td></tr><tr class="even"><td><code>dark</code></td><td>Show a dark scrollbar, which can be either a dark variant of scrollbar provided by the platform, or a custom scrollbar with dark colors.</td></tr><tr class="odd"><td><code>light</code></td><td>Show a light scrollbar, which can be either a light variant of scrollbar provided by the platform, or a custom scrollbar with light colors.</td></tr><tr class="even"><td><code>&lt;color&gt; &lt;color&gt;</code></td><td>Applies the first color to the scrollbar thumb, the second to the scrollbar track.</td></tr></tbody></table>

**Note**: User Agents must apply any `scrollbar-color` value set on the root element to the viewport.

## Accessibility concerns

When using `scrollbar-color` property with specific color values, authors should ensure the specified colors have enough contrast between them. For keyword values, UAs should ensure the colors they use have enough contrast. See [Techniques for WCAG 2.0: G183: Using a contrast ratio of 3:1](https://www.w3.org/TR/WCAG20-TECHS/G183.html).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>scrolling boxes</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="color_value#interpolation">color</a></td></tr></tbody></table>

## Formal syntax

    auto | dark | light | <color>{2}where
    <color> = <rgb()> | <rgba()> | <hsl()> | <hsla()> | <hex-color> | <named-color> | currentcolor | <deprecated-system-color>where
    <rgb()> = rgb( <percentage>{3} [ / <alpha-value> ]? ) | rgb( <number>{3} [ / <alpha-value> ]? ) | rgb( <percentage>#{3} , <alpha-value>? ) | rgb( <number>#{3} , <alpha-value>? )
    <rgba()> = rgba( <percentage>{3} [ / <alpha-value> ]? ) | rgba( <number>{3} [ / <alpha-value> ]? ) | rgba( <percentage>#{3} , <alpha-value>? ) | rgba( <number>#{3} , <alpha-value>? )
    <hsl()> = hsl( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsl( <hue>, <percentage>, <percentage>, <alpha-value>? )
    <hsla()> = hsla( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsla( <hue>, <percentage>, <percentage>, <alpha-value>? )where
    <alpha-value> = <number> | <percentage>
    <hue> = <number> | <angle>

## Examples

### Coloring overflow scrollbars

#### CSS

    .scroller {
      width: 300px;
      height: 100px;
      overflow-y: scroll;
      scrollbar-color: rebeccapurple green;
    }

#### HTML

    <div class="scroller">Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi welsh onion daikon amaranth tatsoi tomatillo melon azuki bean garlic. Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette tatsoi pea sprouts fava bean collard greens dandelion okra wakame tomato. Dandelion cucumber earthnut pea peanut soko zucchini.</div>

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-scrollbars-1/#scrollbar-color">CSS Scrollbars Level 1<br />
<span class="small">The definition of 'scrollbar-color' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`scrollbar-color`

No

No

64

On macOS, you need to set the _General_ &gt; _Show scroll bars_ setting in System Preferences to "Always" for this property to have any effect.

63

No

No

No

No

No

64

63

No

No

No

## See also

- [`scrollbar-width`](scrollbar-width)
- [`overflow`](overflow)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scrollbar-color" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/scrollbar-color</a>
