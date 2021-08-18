# box-shadow

The `box-shadow` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property adds shadow effects around an element's frame. You can set multiple effects separated by commas. A box shadow is described by X and Y offsets relative to the element, blur and spread radius, and color.

The `box-shadow` property enables you to cast a drop shadow from the frame of almost any element. If a [`border-radius`](border-radius) is specified on the element with a box shadow, the box shadow takes on the same rounded corners. The z-ordering of multiple box shadows is the same as multiple [text shadows](text-shadow) (the first specified shadow is on top).

[Box-shadow generator](css_background_and_borders/box-shadow_generator) is an interactive tool allowing you to generate a `box-shadow`.

## Syntax

    /* Keyword values */
    box-shadow: none;

    /* offset-x | offset-y | color */
    box-shadow: 60px -16px teal;

    /* offset-x | offset-y | blur-radius | color */
    box-shadow: 10px 5px 5px black;

    /* offset-x | offset-y | blur-radius | spread-radius | color */
    box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);

    /* inset | offset-x | offset-y | color */
    box-shadow: inset 5em 1em gold;

    /* Any number of shadows, separated by commas */
    box-shadow: 3px 3px red, -1em 0 0.4em olive;

    /* Global keywords */
    box-shadow: inherit;
    box-shadow: initial;
    box-shadow: unset;

Specify a single box-shadow using:

- Two, three, or four `<length>` values.
  - If only two values are given, they are interpreted as `<offset-x><offset-y>` values.
  - If a third value is given, it is interpreted as a `<blur-radius>`.
  - If a fourth value is given, it is interpreted as a `<spread-radius>`.
- Optionally, the `inset` keyword.
- Optionally, a `<color>` value.

To specify multiple shadows, provide a comma-separated list of shadows.

### Values

`inset`  
If not specified (default), the shadow is assumed to be a drop shadow (as if the box were raised above the content).  
The presence of the `inset` keyword changes the shadow to one inside the frame (as if the content was depressed inside the box). Inset shadows are drawn inside the border (even transparent ones), above the background, but below content.

`<offset-x>` `<offset-y>`  
These are two [`<length>`](length) values to set the shadow offset. `<offset-x>` specifies the horizontal distance. Negative values place the shadow to the left of the element. `<offset-y>` specifies the vertical distance. Negative values place the shadow above the element. See [`<length>`](length) for possible units.  
If both values are `0`, the shadow is placed behind the element (and may generate a blur effect if `<blur-radius>` and/or `<spread-radius>` is set).

`<blur-radius>`  
This is a third [`<length>`](length) value. The larger this value, the bigger the blur, so the shadow becomes bigger and lighter. Negative values are not allowed. If not specified, it will be `0` (the shadow's edge is sharp). The specification does not include an exact algorithm for how the blur radius should be calculated, however, it does elaborate as follows:

> …for a long, straight shadow edge, this should create a color transition the length of the blur distance that is perpendicular to and centered on the shadow’s edge, and that ranges from the full shadow color at the radius endpoint inside the shadow to fully transparent at the endpoint outside it.

`<spread-radius>`  
This is a fourth [`<length>`](length) value. Positive values will cause the shadow to expand and grow bigger, negative values will cause the shadow to shrink. If not specified, it will be `0` (the shadow will be the same size as the element).

`<color>`  
See [`<color>`](color_value) values for possible keywords and notations.  
If not specified, it defaults to [`<color_value#currentcolor_keyword>`](color_value#currentcolor_keyword).

### Interpolation

Each shadow in the list (treating `none` as a 0-length list) is interpolated via the color (as color) component, and x, y, blur, and (when appropriate) spread (as length) components. For each shadow, if both input shadows are or are not `inset`, then the interpolated shadow must match the input shadows in that regard. If any pair of input shadows has one `inset` and the other not `inset`, the entire shadow list is uninterpolated. If the lists of shadows have different lengths, then the shorter list is padded at the end with shadows whose color is `transparent`, all lengths are `0`, and whose `inset` (or not) matches the longer list.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>any length made absolute; any specified color computed; otherwise as specified</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="#Interpolation">shadow list</a></td></tr></tbody></table>

## Formal syntax

    none | <shadow>#where
    <shadow> = inset? && <length>{2,4} && <color>?where
    <color> = <rgb()> | <rgba()> | <hsl()> | <hsla()> | <hex-color> | <named-color> | currentcolor | <deprecated-system-color>where
    <rgb()> = rgb( <percentage>{3} [ / <alpha-value> ]? ) | rgb( <number>{3} [ / <alpha-value> ]? ) | rgb( <percentage>#{3} , <alpha-value>? ) | rgb( <number>#{3} , <alpha-value>? )
    <rgba()> = rgba( <percentage>{3} [ / <alpha-value> ]? ) | rgba( <number>{3} [ / <alpha-value> ]? ) | rgba( <percentage>#{3} , <alpha-value>? ) | rgba( <number>#{3} , <alpha-value>? )
    <hsl()> = hsl( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsl( <hue>, <percentage>, <percentage>, <alpha-value>? )
    <hsla()> = hsla( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsla( <hue>, <percentage>, <percentage>, <alpha-value>? )where
    <alpha-value> = <number> | <percentage>
    <hue> = <number> | <angle>

## Examples

### Setting three shadows

In this example, we include three shadows: an inset shadow, a regular drop shadow, and a 2px shadow that creates a border effect (we could have used an [`outline`](outline) instead for that third shadow).

#### HTML

    <blockquote><q>You may shoot me with your words,<br/>
    You may cut me with your eyes,<br/>
    You may kill me with your hatefulness,<br/>
    But still, like air, I'll rise.</q>
    <p>&mdash; Maya Angelou</p>
    </blockquote>

#### CSS

    blockquote {
      padding: 20px;
      box-shadow:
           inset 0 -3em 3em rgba(0,0,0,0.1),
                 0 0  0 2px rgb(255,255,255),
                 0.3em 0.3em 1em rgba(0,0,0,0.3);
    }

#### Result

### Setting zero for offset and blur

When the `x-offset`, `y-offset`, and `blur` are all zero, the box shadow will be a solid-colored outline of equal-size on all sides. The shadows are drawn back to front, so the first shadow sits on top of subsequent shadows. When the `border-radius` is set to 0, as is the default, the corners of the shadow will be, well, corners. Had we put in a `border-radius` of any other value, the corners would have been rounded.

We added a margin the size of the widest box-shadow to ensure the shadow doesn't overlap adjacent elements or go beyond the border of the containing box. A box-shadow does not impact [box model](css_box_model) dimensions.

#### HTML

    <div><p>Hello World</p></div>

#### CSS

    p {
      box-shadow: 0 0 0 2em #F4AAB9,
                  0 0 0 4em #66CCFF;
      margin: 4em;
      padding:1em;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#box-shadow">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'box-shadow' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`box-shadow`

10

Shadows affect layout in this browser. For example, if you cast an outer shadow to a box with a `width` of `100%`, then you'll see a scrollbar.

1

12

4

Shadows affect layout in this browser. For example, if you cast an outer shadow to a box with a `width` of `100%`, then you'll see a scrollbar.

3.5-13

49

44

9

\["To use `box-shadow` in Internet Explorer 9 or later, you must set [`border-collapse`](https://developer.mozilla.org/docs/Web/CSS/border-collapse) to `separate`.", "Since version 5.5, Internet Explorer supports Microsoft's [DropShadow](http://msdn.microsoft.com/en-us/library/ms532985%28VS.85,loband%29.aspx) and [Shadow Filter](http://msdn.microsoft.com/en-us/library/ms533086%28VS.85,loband%29.aspx). You can use this proprietary extension to cast a drop shadow (though the syntax and the effect are different from CSS3)"\]

10.5

Shadows affect layout in this browser. For example, if you cast an outer shadow to a box with a `width` of `100%`, then you'll see a scrollbar.

5.1

Shadows affect layout in this browser. For example, if you cast an outer shadow to a box with a `width` of `100%`, then you'll see a scrollbar.

3

≤37

Shadows affect layout in this browser. For example, if you cast an outer shadow to a box with a `width` of `100%`, then you'll see a scrollbar.

≤37

18

Shadows affect layout in this browser. For example, if you cast an outer shadow to a box with a `width` of `100%`, then you'll see a scrollbar.

18

4

Shadows affect layout in this browser. For example, if you cast an outer shadow to a box with a `width` of `100%`, then you'll see a scrollbar.

4-14

49

44

14

Shadows affect layout in this browser. For example, if you cast an outer shadow to a box with a `width` of `100%`, then you'll see a scrollbar.

14

5

Shadows affect layout in this browser. For example, if you cast an outer shadow to a box with a `width` of `100%`, then you'll see a scrollbar.

1

1.0

Shadows affect layout in this browser. For example, if you cast an outer shadow to a box with a `width` of `100%`, then you'll see a scrollbar.

1.0

`inset`

10

1

12

4

3.5-13

9

\["To use `box-shadow` in Internet Explorer 9 or later, you must set [`border-collapse`](https://developer.mozilla.org/docs/Web/CSS/border-collapse) to `separate`.", "`inset` must be the last keyword in the declaration."\]

10.5

5.1

5

≤37

≤37

18

18

4

4-14

14

14

5

4.2

1.0

1.0

`multiple_shadows`

10

1

12

4

3.5-13

9

To use `box-shadow` in Internet Explorer 9 or later, you must set [`border-collapse`](https://developer.mozilla.org/docs/Web/CSS/border-collapse) to `separate`.

10.5

5.1

3

≤37

≤37

18

18

4

4-14

14

14

5

1

1.0

1.0

`spread_radius`

10

1

12

4

3.5-13

9

To use `box-shadow` in Internet Explorer 9 or later, you must set [`border-collapse`](https://developer.mozilla.org/docs/Web/CSS/border-collapse) to `separate`.

10.5

5.1

5

≤37

≤37

18

18

4

4-14

14

14

5

4.2

1.0

1.0

## See also

- The [`<color>`](color_value) data type
- Other color-related properties: [`color`](color), [`background-color`](background-color), [`border-color`](border-color), [`outline-color`](outline-color), [`text-decoration-color`](text-decoration-color), [`text-emphasis-color`](text-emphasis-color), [`caret-color`](caret-color), and [`column-rule-color`](column-rule-color)
- [`text-shadow`](text-shadow)
- [Applying color to HTML elements using CSS](https://developer.mozilla.org/en-US/docs/Web/HTML/Applying_color)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow</a>
