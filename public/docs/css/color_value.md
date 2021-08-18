# &lt;color&gt;

The `<color>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types) represents a color in the [sRGB color space](https://en.wikipedia.org/wiki/SRGB). A `<color>` may also include an [alpha-channel](https://en.wikipedia.org/wiki/Alpha_compositing) _transparency value_, indicating how the color should [composite](https://www.w3.org/TR/2003/REC-SVG11-20030114/masking.html#SimpleAlphaBlending) with its background.

A `<color>` can be defined in any of the following ways:

- Using a keyword (such as `blue` or `transparent`)
- Using the [RGB cubic-coordinate](https://en.wikipedia.org/wiki/RGB_color_model#Geometric_representation) system (via the \#-hexadecimal or the `rgb()` and `rgba()` functional notations)
- Using the [HSL cylindrical-coordinate](https://en.wikipedia.org/wiki/HSL_and_HSV) system (via the `hsl()` and `hsla()` functional notations)

**Note:** This article describes the `<color>` data type in detail. To learn more about using color in HTML, see [Applying color to HTML elements using CSS](https://developer.mozilla.org/en-US/docs/Web/HTML/Applying_color).

## Syntax

The `<color>` data type is specified using one of the options listed below.

**Note:** Although `<color>` values are precisely defined, their actual appearance may vary (sometimes significantly) from device to device. This is because most devices are not calibrated, and some browsers do not support output devices' [color profiles](https://en.wikipedia.org/wiki/ICC_profile).

### Color keywords

Color keywords are case-insensitive identifiers that represent a specific color, such as `red`, `blue`, `black`, or `lightseagreen`. Although the names more or less describes their respective colors, they are essentially artificial, without a strict rationale behind the names used.

There are a few caveats to consider when using color keywords:

- [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) only recognizes the 16 basic color keywords found in CSS1, using a specific algorithm to convert unrecognized values (often to completely different colors). The other color keywords should only be used in CSS and [SVG](https://developer.mozilla.org/en-US/docs/Web/SVG).
- Unlike HTML, CSS will completely ignore unknown keywords.
- The color keywords all represent plain, solid colors, without transparency.
- Several keywords are aliases for each other:
  - `aqua` / `cyan`
  - `fuchsia` / `magenta`
  - `darkgray` / `darkgrey`
  - `darkslategray` / `darkslategrey`
  - `dimgray` / `dimgrey`
  - `lightgray` / `lightgrey`
  - `lightslategray` / `lightslategrey`
  - `gray` / `grey`
  - `slategray` / `slategrey`
- Though many keywords have been adapted from [X11](https://en.wikipedia.org/wiki/X_Window_System), their RGB values may differ from the corresponding color on X11 systems since manufacturers sometimes tailor X11 colors to their specific hardware.

**Note:** The list of accepted keywords has undergone many changes during the evolution of CSS:

- CSS Level 1 only included 16 basic colors, called the _VGA colors_ as they were taken from the set of displayable colors on [VGA](https://en.wikipedia.org/wiki/VGA) graphics cards.
- CSS Level 2 added the `orange` keyword.
- Although various colors not in the specification (mostly adapted from the X11 colors list) were supported by early browsers, it wasn't until SVG 1.0 and CSS Colors Level 3 that they were formally defined. They are called the _extended color keywords_, the _X11 colors_, or the _SVG colors_.
- CSS Colors Level 4 added the `rebeccapurple` keyword [to honor web pioneer Eric Meyer](https://codepen.io/trezy/post/honoring-a-great-man).

Specification

Keyword

RGB hex value

Live keyword

[CSS Level 1](https://www.w3.org/TR/CSS1/)

`black`

`#000000`

`silver`

`#c0c0c0`

`gray`

`#808080`

`white`

`#ffffff`

`maroon`

`#800000`

`red`

`#ff0000`

`purple`

`#800080`

`fuchsia`

`#ff00ff`

`green`

`#008000`

`lime`

`#00ff00`

`olive`

`#808000`

`yellow`

`#ffff00`

`navy`

`#000080`

`blue`

`#0000ff`

`teal`

`#008080`

`aqua`

`#00ffff`

[CSS Level 2 (Revision 1)](https://www.w3.org/TR/CSS2/)

`orange`

`#ffa500`

[CSS Color Module Level 3](https://drafts.csswg.org/css-color-3/)

`aliceblue`

`#f0f8ff`

`antiquewhite`

`#faebd7`

`aquamarine`

`#7fffd4`

`azure`

`#f0ffff`

`beige`

`#f5f5dc`

`bisque`

`#ffe4c4`

`blanchedalmond`

`#ffebcd`

`blueviolet`

`#8a2be2`

`brown`

`#a52a2a`

`burlywood`

`#deb887`

`cadetblue`

`#5f9ea0`

`chartreuse`

`#7fff00`

`chocolate`

`#d2691e`

`coral`

`#ff7f50`

`cornflowerblue`

`#6495ed`

`cornsilk`

`#fff8dc`

`crimson`

`#dc143c`

`cyan`  
(synonym of `aqua`)

`#00ffff`

`darkblue`

`#00008b`

`darkcyan`

`#008b8b`

`darkgoldenrod`

`#b8860b`

`darkgray`

`#a9a9a9`

`darkgreen`

`#006400`

`darkgrey`

`#a9a9a9`

`darkkhaki`

`#bdb76b`

`darkmagenta`

`#8b008b`

`darkolivegreen`

`#556b2f`

`darkorange`

`#ff8c00`

`darkorchid`

`#9932cc`

`darkred`

`#8b0000`

`darksalmon`

`#e9967a`

`darkseagreen`

`#8fbc8f`

`darkslateblue`

`#483d8b`

`darkslategray`

`#2f4f4f`

`darkslategrey`

`#2f4f4f`

`darkturquoise`

`#00ced1`

`darkviolet`

`#9400d3`

`deeppink`

`#ff1493`

`deepskyblue`

`#00bfff`

`dimgray`

`#696969`

`dimgrey`

`#696969`

`dodgerblue`

`#1e90ff`

`firebrick`

`#b22222`

`floralwhite`

`#fffaf0`

`forestgreen`

`#228b22`

`gainsboro`

`#dcdcdc`

`ghostwhite`

`#f8f8ff`

`gold`

`#ffd700`

`goldenrod`

`#daa520`

`greenyellow`

`#adff2f`

`grey`

`#808080`

`honeydew`

`#f0fff0`

`hotpink`

`#ff69b4`

`indianred`

`#cd5c5c`

`indigo`

`#4b0082`

`ivory`

`#fffff0`

`khaki`

`#f0e68c`

`lavender`

`#e6e6fa`

`lavenderblush`

`#fff0f5`

`lawngreen`

`#7cfc00`

`lemonchiffon`

`#fffacd`

`lightblue`

`#add8e6`

`lightcoral`

`#f08080`

`lightcyan`

`#e0ffff`

`lightgoldenrodyellow`

`#fafad2`

`lightgray`

`#d3d3d3`

`lightgreen`

`#90ee90`

`lightgrey`

`#d3d3d3`

`lightpink`

`#ffb6c1`

`lightsalmon`

`#ffa07a`

`lightseagreen`

`#20b2aa`

`lightskyblue`

`#87cefa`

`lightslategray`

`#778899`

`lightslategrey`

`#778899`

`lightsteelblue`

`#b0c4de`

`lightyellow`

`#ffffe0`

`limegreen`

`#32cd32`

`linen`

`#faf0e6`

`magenta`  
(synonym of `fuchsia`)

`#ff00ff`

`mediumaquamarine`

`#66cdaa`

`mediumblue`

`#0000cd`

`mediumorchid`

`#ba55d3`

`mediumpurple`

`#9370db`

`mediumseagreen`

`#3cb371`

`mediumslateblue`

`#7b68ee`

`mediumspringgreen`

`#00fa9a`

`mediumturquoise`

`#48d1cc`

`mediumvioletred`

`#c71585`

`midnightblue`

`#191970`

`mintcream`

`#f5fffa`

`mistyrose`

`#ffe4e1`

`moccasin`

`#ffe4b5`

`navajowhite`

`#ffdead`

`oldlace`

`#fdf5e6`

`olivedrab`

`#6b8e23`

`orangered`

`#ff4500`

`orchid`

`#da70d6`

`palegoldenrod`

`#eee8aa`

`palegreen`

`#98fb98`

`paleturquoise`

`#afeeee`

`palevioletred`

`#db7093`

`papayawhip`

`#ffefd5`

`peachpuff`

`#ffdab9`

`peru`

`#cd853f`

`pink`

`#ffc0cb`

`plum`

`#dda0dd`

`powderblue`

`#b0e0e6`

`rosybrown`

`#bc8f8f`

`royalblue`

`#4169e1`

`saddlebrown`

`#8b4513`

`salmon`

`#fa8072`

`sandybrown`

`#f4a460`

`seagreen`

`#2e8b57`

`seashell`

`#fff5ee`

`sienna`

`#a0522d`

`skyblue`

`#87ceeb`

`slateblue`

`#6a5acd`

`slategray`

`#708090`

`slategrey`

`#708090`

`snow`

`#fffafa`

`springgreen`

`#00ff7f`

`steelblue`

`#4682b4`

`tan`

`#d2b48c`

`thistle`

`#d8bfd8`

`tomato`

`#ff6347`

`turquoise`

`#40e0d0`

`violet`

`#ee82ee`

`wheat`

`#f5deb3`

`whitesmoke`

`#f5f5f5`

`yellowgreen`

`#9acd32`

[CSS Color Module Level 4](https://drafts.csswg.org/css-color/)

[`rebeccapurple`](https://en.wikipedia.org/wiki/Eric_A._Meyer#Personal_life)

`#663399`

### `transparent` keyword

The `transparent` keyword represents a fully transparent color. This makes the background behind the colored item completely visible. Technically, `transparent` is a shortcut for `rgba(0,0,0,0)`.

**Compatibility note:** To prevent unexpected behavior, such as in a [`<gradient>`](gradient), the current CSS spec states that `transparent` should be calculated in the [alpha-premultiplied color space](https://www.w3.org/TR/2012/CR-css3-images-20120417/#color-stop-syntax). However, be aware that older browsers may treat it as black with an alpha value of `0`.

**Historical note:** `transparent` wasn't a true color in CSS Level 2 (Revision 1). It was a special keyword that could be used instead of a regular `<color>` value on two CSS properties: [`background`](background) and [`border`](border). It was essentially added to allow developers to override an inherited solid color. With the advent of alpha channels in CSS Colors Level 3, `transparent` was redefined as a true color. It can now be used wherever a `<color>` value can be used.

### `currentcolor` keyword

The `currentcolor` keyword represents the value of an element's [`color`](color) property. This lets you use the `color` value on properties that do not receive it by default.

If `currentcolor` is used as the value of the `color` property, it instead takes its value from the inherited value of the `color` property.

#### currentcolor example

    <div style="color:blue; border: 1px dashed currentcolor;">
      The color of this text is blue.
      <div style="background:currentcolor; height:9px;"></div>
      This block is surrounded by a blue border.
    </div>

### RGB colors

The RGB color model defines a given color according to its red, green, and blue components. An optional alpha component represents the color's transparency.

#### Syntax

RGB colors can be expressed through both hexadecimal (prefixed with `#`) and functional (`rgb()`, `rgba()`) notations.

**Note:** As of CSS Colors Level 4, `rgba()` is an alias for `rgb()`. In browsers that implement the Level 4 standard, they accept the same parameters and behave the same way.

Hexadecimal notation: `#RRGGBB[AA]`  
`R` (red), `G` (green), `B` (blue), and `A` (alpha) are hexadecimal characters (0–9, A–F). `A` is optional. For example, `#ff0000` is equivalent to `#ff0000ff`.

Hexadecimal notation: `#RGB[A]`  
`R` (red), `G` (green), `B` (blue), and `A` (alpha) are hexadecimal characters (0–9, A–F). `A` is optional. The three-digit notation (`#RGB`) is a shorter version of the six-digit form (`#RRGGBB`). For example, `#f09` is the same color as `#ff0099`. Likewise, the four-digit RGB notation (`#RGBA`) is a shorter version of the eight-digit form (`#RRGGBBAA`). For example, `#0f38` is the same color as `#00ff3388`.

Functional notation: `rgb[a](R, G, B[, A])`  
`R` (red), `G` (green), and `B` (blue) can be either [`<number>`](number)s or [`<percentage>`](percentage)s, where the number `255` corresponds to `100%`. `A` (alpha) can be a [`<number>`](number) between `0` and `1`, or a [`<percentage>`](percentage), where the number `1` corresponds to `100%` (full opacity).

Functional notation: `rgb[a](R G B[ / A])`  
CSS Colors Level 4 adds support for space-separated values in the functional notation.

### HSL colors

The HSL color model defines a given color according to its hue, saturation, and lightness components. An optional alpha component represents the color's transparency.

Many designers find HSL more intuitive than RGB, since it allows hue, saturation, and lightness to each be adjusted independently. HSL can also make it easier to create a set of matching colors (such as when you want multiple shades of a single hue).

#### Syntax

HSL colors are expressed through the functional `hsl()` and `hsla()` notations.

**Note**: As of CSS Colors Level 4, `hsla()` is an alias for `hsl()`. In browsers that implement the Level 4 standard, they accept the same parameters and behave the same way.

Functional notation: `hsl[a](H, S, L[, A])`  
`H` (hue) is an [`<angle>`](angle) of the color circle given in `deg`s, `rad`s, `grad`s, or `turn`s in [CSS Color Module Level 4](https://drafts.csswg.org/css-color/#the-hsl-notation). When written as a unitless [`<number>`](number), it is interpreted as degrees, as specified in [CSS Color Module Level 3](https://drafts.csswg.org/css-color-3/#hsl-color). By definition, red=0deg=360deg, with the other colors spread around the circle, so green=120deg, blue=240deg, etc. As an `<angle>`, it implicitly wraps around such that -120deg=240deg, 480deg=120deg, -1turn=1turn, etc.

`S` (saturation) and `L` (lightness) are percentages. `100%` **saturation** is completely saturated, while `0%` is completely unsaturated (gray). `100%` **lightness** is white, `0%` lightness is black, and `50%` lightness is “normal.”

`A` (alpha) can be a [`<number>`](number) between `0` and `1`, or a [`<percentage>`](percentage), where the number `1` corresponds to `100%` (full opacity).

Functional notation: `hsl[a](H S L[ / A])`  
CSS Colors Level 4 adds support for space-separated values in the functional notation.

### System Colors

In _forced colors mode_ (detectable with the [forced-colors](@media/forced-colors) media query), most colors are restricted into a user- and browser-defined palette. These system colors are exposed by the following keywords, which can be used to ensure that the rest of the page integrates well with the restricted palette. These values may also be used in other contexts, but are not widely supported by browsers.

The keywords in the following list are defined by the CSS Color Module Level 4 specification.

Note that these keywords are _case insensitive_, but are listed here with mixed case for readability.

ActiveText  
Text of active links

ButtonFace  
Background color of controls

ButtonText  
Foreground color of controls

Canvas  
Background of application content or documents

CanvasText  
Foreground color in application content or documents

Field  
Background of input fields

FieldText  
Text in input fields

GrayText  
Foreground color for disabled items (e.g. a disabled control)

Highlight  
Background of selected items

HighlightText  
Foreground color of selected items

LinkText  
Text of non-active, non-visited links

Mark  
Background of text that has been specially marked (such as by the HTML `mark` element)

MarkText  
Text that has been specially marked (such as by the HTML `mark` element)

VisitedText  
Text of visited links

#### Deprecated system color keywords

The following keywords were defined in earlier versions of the CSS Color Module. They are now deprecated. <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> for use on public web pages.

ActiveBorder  
Active window border.

ActiveCaption  
Active window caption. Should be used with `CaptionText` as foreground color.

AppWorkspace  
Background color of multiple document interface.

Background  
Desktop background.

ButtonHighlight  
The color of the border facing the light source for 3-D elements that appear 3-D due to that layer of surrounding border.

ButtonShadow  
The color of the border away from the light source for 3-D elements that appear 3-D due to that layer of surrounding border.

CaptionText  
Text in caption, size box, and scrollbar arrow box. Should be used with the `ActiveCaption` background color.

InactiveBorder  
Inactive window border.

InactiveCaption  
Inactive window caption. Should be used with the `InactiveCaptionText` foreground color.

InactiveCaptionText  
Color of text in an inactive caption. Should be used with the `InactiveCaption` background color.

InfoBackground  
Background color for tooltip controls. Should be used with the `InfoText` foreground color.

InfoText  
Text color for tooltip controls. Should be used with the `InfoBackground` background color.

Menu  
Menu background. Should be used with the `MenuText` or `-moz-MenuBarText` foreground color.

MenuText  
Text in menus. Should be used with the `Menu` background color.

Scrollbar  
Background color of scroll bars.

ThreeDDarkShadow  
The color of the darker (generally outer) of the two borders away from the light source for 3-D elements that appear 3-D due to two concentric layers of surrounding border.

ThreeDFace  
The face background color for 3-D elements that appear 3-D due to two concentric layers of surrounding border. Should be used with the `ButtonText` foreground color.

ThreeDHighlight  
The color of the lighter (generally outer) of the two borders facing the light source for 3-D elements that appear 3-D due to two concentric layers of surrounding border.

ThreeDLightShadow  
The color of the darker (generally inner) of the two borders facing the light source for 3-D elements that appear 3-D due to two concentric layers of surrounding border.

ThreeDShadow  
The color of the lighter (generally inner) of the two borders away from the light source for 3-D elements that appear 3-D due to two concentric layers of surrounding border.

Window  
Window background. Should be used with the `WindowText` foreground color.

WindowFrame  
Window frame.

WindowText  
Text in windows. Should be used with the `Window` background color.

### Mozilla System Color Extensions

-moz-ButtonDefault  
The border color that goes around buttons that represent the default action for a dialog box.

-moz-ButtonHoverFace  
The background color of a button that the mouse pointer is over (which would be `ThreeDFace` or `ButtonFace` when the mouse pointer is not over it). Should be used with the `-moz-ButtonHoverText` foreground color.

-moz-ButtonHoverText  
The text color of a button that the mouse pointer is over (which would be ButtonText when the mouse pointer is not over it). Should be used with the `-moz-ButtonHoverFace background` color.

-moz-CellHighlight  
Background color for selected item in a tree widget. Should be used with the `-moz-CellHighlightText` foreground color. See also `-moz-html-CellHighlight`.

-moz-CellHighlightText  
Text color for a selected item in a tree. Should be used with the `-moz-CellHighlight background` color. See also `-moz-html-CellHighlightText`.

-moz-Combobox  
Background color for combo-boxes. Should be used with the `-moz-ComboboxText` foreground color. In versions prior to 1.9.2, use `-moz-Field` instead.

-moz-ComboboxText  
Text color for combo-boxes. Should be used with the `-moz-Combobox` background color. In versions prior to 1.9.2, use `-moz-FieldText` instead.

-moz-Dialog  
Background color for dialog boxes. Should be used with the `-moz-DialogText` foreground color.

-moz-DialogText  
Text color for dialog boxes. Should be used with the `-moz-Dialog` background color.

-moz-dragtargetzone  
-moz-EvenTreeRow  
Background color for even-numbered rows in a tree. Should be used with the `-moz-FieldText` foreground color. In Gecko versions prior to 1.9, use `-moz-Field`. See also `-moz-OddTreeRow`.

-moz-html-CellHighlight  
Background color for highlighted item in HTML [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select)s. Should be used with the `-moz-html-CellHighlightText` foreground color. Prior to Gecko 1.9, use `-moz-CellHighlight`.

-moz-html-CellHighlightText  
Text color for highlighted items in HTML [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select)s. Should be used with the `-moz-html-CellHighlight` background color. Prior to Gecko 1.9, use `-moz-CellHighlightText`.

-moz-mac-accentdarkestshadow  
-moz-mac-accentdarkshadow  
-moz-mac-accentface  
-moz-mac-accentlightesthighlight  
-moz-mac-accentlightshadow  
-moz-mac-accentregularhighlight  
-moz-mac-accentregularshadow  
-moz-mac-chrome-active  
-moz-mac-chrome-inactive  
-moz-mac-focusring  
-moz-mac-menuselect  
-moz-mac-menushadow  
-moz-mac-menutextselect  
-moz-MenuHover  
Background color for hovered menu items. Often similar to `Highlight`. Should be used with the `-moz-MenuHoverText` or `-moz-MenuBarHoverText` foreground color.

-moz-MenuHoverText  
Text color for hovered menu items. Often similar to `HighlightText`. Should be used with the `-moz-MenuHover` background color.

-moz-MenuBarText  
Text color in menu bars. Often similar to `MenuText`. Should be used on top of `Menu` background.

-moz-MenuBarHoverText  
Color for hovered text in menu bars. Often similar to `-moz-MenuHoverText`. Should be used on top of `-moz-MenuHover` background.

-moz-nativehyperlinktext  
Default platform hyperlink color.

-moz-OddTreeRow  
Background color for odd-numbered rows in a tree. Should be used with the `-moz-FieldText` foreground color. In Gecko versions prior to 1.9, use `-moz-Field`. See also `-moz-EvenTreeRow`.

-moz-win-communicationstext  
Should be used for text in objects with `appearance`: -moz-win-communications-toolbox;.

-moz-win-mediatext  
Should be used for text in objects with `appearance`: -moz-win-media-toolbox.

-moz-win-accentcolor  
Used to access the Windows 10 custom accent color that you can set on the start menu, taskbar, title bars, etc.

-moz-win-accentcolortext  
Used to access the color of text placed over the Windows 10 custom accent color in the start menu, taskbar, title bars, etc.

### Mozilla Color Preference Extensions

-moz-activehyperlinktext  
User's preference for text color of active links. Should be used with the default document background color.

-moz-default-background-color  
User's preference for the document background color.

-moz-default-color  
User's preference for the text color.

-moz-hyperlinktext  
User's preference for the text color of unvisited links. Should be used with the default document background color.

-moz-visitedhyperlinktext  
User's preference for the text color of visited links. Should be used with the default document background color.

## Interpolation

In animations and [gradients](css_images/using_css_gradients), `<color>` values are interpolated on each of their red, green, and blue components. Each component is interpolated as a real, floating-point number. Note that interpolation of colors happens in the [alpha-premultiplied sRGBA color space](https://www.gimp.org/docs/plug-in/appendix-alpha.html) to prevent unexpected gray colors from appearing. In animations, the interpolation's speed is determined by the [timing function](easing-function).

## Accessibility considerations

Some people have difficulty distinguishing colors. The [WCAG 2.0](https://www.w3.org/TR/WCAG/#visual-audio-contrast) recommendation strongly advises against using color as the only means of conveying a specific message, action, or result. See [Color and color contrast](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#color_and_color_contrast) for more information.

## Examples

### Color value tester

In this example we provide a `<div>` and a text input. Entering a valid color into the input causes the `<div>` to adopt that color, allowing you to test our color values.

#### HTML

    <div></div>
    <hr>
    <label for="color">Enter a valid color value:</label>
    <input type="text" id="color">

#### CSS

    div {
      width: 100%;
      height: 200px;
    }

#### Result

### RGB syntax variations

This example shows the many ways in which a single color can be created with the various RGB color syntaxes.

    /* These syntax variations all specify the same color: a fully opaque hot pink. */

    /* Hexadecimal syntax */
    #f09
    #F09
    #ff0099
    #FF0099

    /* Functional syntax */
    rgb(255,0,153)
    rgb(255, 0, 153)
    rgb(255, 0, 153.0)
    rgb(100%,0%,60%)
    rgb(100%, 0%, 60%)
    rgb(100%, 0, 60%) /* ERROR! Don't mix numbers and percentages. */
    rgb(255 0 153)

    /* Hexadecimal syntax with alpha value */
    #f09f
    #F09F
    #ff0099ff
    #FF0099FF

    /* Functional syntax with alpha value */
    rgb(255, 0, 153, 1)
    rgb(255, 0, 153, 100%)

    /* Whitespace syntax */
    rgb(255 0 153 / 1)
    rgb(255 0 153 / 100%)

    /* Functional syntax with floats value */
    rgb(255, 0, 153.6, 1)
    rgb(1e2, .5e1, .5e0, +.25e2%)

### RGB transparency variations

    /* Hexadecimal syntax */
    #3a30                    /*   0% opaque green */
    #3A3F                    /* full opaque green */
    #33aa3300                /*   0% opaque green */
    #33AA3380                /*  50% opaque green */

    /* Functional syntax */
    rgba(51, 170, 51, .1)    /*  10% opaque green */
    rgba(51, 170, 51, .4)    /*  40% opaque green */
    rgba(51, 170, 51, .7)    /*  70% opaque green */
    rgba(51, 170, 51,  1)    /* full opaque green */

    /* Whitespace syntax */
    rgba(51 170 51 / 0.4)    /*  40% opaque green */
    rgba(51 170 51 / 40%)    /*  40% opaque green */

    /* Functional syntax with floats value */
    rgba(255, 0, 153.6, 1)
    rgba(1e2, .5e1, .5e0, +.25e2%)

### HSL syntax variations

    /* These examples all specify the same color: a lavender. */
    hsl(270,60%,70%)
    hsl(270, 60%, 70%)
    hsl(270 60% 70%)
    hsl(270deg, 60%, 70%)
    hsl(4.71239rad, 60%, 70%)
    hsl(.75turn, 60%, 70%)

    /* These examples all specify the same color: a lavender that is 15% opaque. */
    hsl(270, 60%, 50%, .15)
    hsl(270, 60%, 50%, 15%)
    hsl(270 60% 50% / .15)
    hsl(270 60% 50% / 15%)

### Fully saturated colors

<table><thead><tr class="header"><th>Notation</th><th>Description</th><th>Live</th></tr></thead><tbody><tr class="odd"><td><code>hsl(0, 100%, 50%)</code></td><td>red</td><td></td></tr><tr class="even"><td><code>hsl(30, 100%, 50%)</code></td><td>orange</td><td></td></tr><tr class="odd"><td><code>hsl(60, 100%, 50%)</code></td><td>yellow</td><td></td></tr><tr class="even"><td><code>hsl(90, 100%, 50%)</code></td><td>lime green</td><td></td></tr><tr class="odd"><td><code>hsl(120, 100%, 50%)</code></td><td>green</td><td></td></tr><tr class="even"><td><code>hsl(150, 100%, 50%)</code></td><td>blue-green</td><td></td></tr><tr class="odd"><td><code>hsl(180, 100%, 50%)</code></td><td>cyan</td><td></td></tr><tr class="even"><td><code>hsl(210, 100%, 50%)</code></td><td>sky blue</td><td></td></tr><tr class="odd"><td><code>hsl(240, 100%, 50%)</code></td><td>blue</td><td></td></tr><tr class="even"><td><code>hsl(270, 100%, 50%)</code></td><td>purple</td><td></td></tr><tr class="odd"><td><code>hsl(300, 100%, 50%)</code></td><td>magenta</td><td></td></tr><tr class="even"><td><code>hsl(330, 100%, 50%)</code></td><td>pink</td><td></td></tr><tr class="odd"><td><code>hsl(360, 100%, 50%)</code></td><td>red</td><td></td></tr></tbody></table>

### Lighter and darker greens

<table><thead><tr class="header"><th>Notation</th><th>Description</th><th>Live</th></tr></thead><tbody><tr class="odd"><td><code>hsl(120, 100%, 0%)</code></td><td>black</td><td></td></tr><tr class="even"><td><code>hsl(120, 100%, 20%)</code></td><td></td><td></td></tr><tr class="odd"><td><code>hsl(120, 100%, 40%)</code></td><td></td><td></td></tr><tr class="even"><td><code>hsl(120, 100%, 60%)</code></td><td></td><td></td></tr><tr class="odd"><td><code>hsl(120, 100%, 80%)</code></td><td></td><td></td></tr><tr class="even"><td><code>hsl(120, 100%, 100%)</code></td><td>white</td><td></td></tr></tbody></table>

### Saturated and desaturated greens

<table><thead><tr class="header"><th>Notation</th><th>Description</th><th>Live</th></tr></thead><tbody><tr class="odd"><td><code>hsl(120, 100%, 50%)</code></td><td>green</td><td></td></tr><tr class="even"><td><code>hsl(120, 80%, 50%)</code></td><td></td><td></td></tr><tr class="odd"><td><code>hsl(120, 60%, 50%)</code></td><td></td><td></td></tr><tr class="even"><td><code>hsl(120, 40%, 50%)</code></td><td></td><td></td></tr><tr class="odd"><td><code>hsl(120, 20%, 50%)</code></td><td></td><td></td></tr><tr class="even"><td><code>hsl(120, 0%, 50%)</code></td><td>gray</td><td></td></tr></tbody></table>

### HSL transparency variations

    hsla(240, 100%, 50%, .05)     /*   5% opaque blue */
    hsla(240, 100%, 50%, .4)      /*  40% opaque blue */
    hsla(240, 100%, 50%, .7)      /*  70% opaque blue */
    hsla(240, 100%, 50%, 1)       /* full opaque blue */

    /* Whitespace syntax */
    hsla(240 100% 50% / .05)      /*   5% opaque blue */

    /* Percentage value for alpha */
    hsla(240 100% 50% / 5%)       /*   5% opaque blue */

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-color/#changes-from-3">CSS Color Module Level 4</a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds <code>rebeccapurple</code>, four- (<code>#RGBA</code>) and eight-digit (<code>#RRGGBBAA</code>) hexadecimal notations, <code>rgba()</code> and <code>hsla()</code> as aliases of <code>rgb()</code> and <code>hsl()</code> (both with identical parameter syntax), space-separated function parameters as an alternative to commas, percentages for alpha values, and angles for the hue component in <code>hsl()</code> colors.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-color-3/#colorunits">CSS Color Module Level 3<br />
<span class="small">The definition of '&lt;color&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Deprecates system colors. Adds SVG colors and <code>rgba()</code>, <code>hsl()</code>, and <code>hsla()</code> functional notations.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/syndata.html#value-def-color">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of '&lt;color&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Adds the <code>orange</code> keyword and system colors.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#color-units">CSS Level 1<br />
<span class="small">The definition of '&lt;color&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition. Includes 16 basic color keywords.</td></tr></tbody></table>

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

`color_value`

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

`alpha`

1

12

3

9

10

3.1

≤37

18

4

10.1

2

1.0

`alpha_hexadecimal_notation`

62

79

49

No

49

9.1

62

62

49

47

9.3

8.0

`color-mix`

No

No

88

No

No

No

No

No

88

No

No

No

`currentcolor`

1

12

1.5

9

9.5

4

37

18

4

14

3.2

1.0

`floats_in_rgb_rgba`

66

79

52

No

53

12.1

66

66

52

47

12.2

9.0

`hsl`

1

12

1

9

9.5

3.1

≤37

18

4

10.1

2

1.0

`hsl_function_accepts_alpha`

65

79

52

No

52

12.1

65

65

52

47

12.2

9.0

`keyword_color_values`

1

12

1

3

Internet Explorer 8 and later support gray color keywords spelled with an _e_ (`grey`, `darkgrey`, `darkslategrey`, `dimgrey`, `lightgrey`, and `lightslategrey`). Internet Explorer 3 to Internet Explorer 7 only support the keywords spelled with _a_ (`gray`, `darkgray`, `darkslategray`, `dimgray`, `lightgray`, and `lightslategray`).

3.5

1

≤37

18

4

10.1

1

1.0

`rebeccapurple`

38

12

33

11

25

9

38

38

33

25

8

3.0

`rgb_function_accepts_alpha`

65

79

52

No

52

12.1

65

65

52

47

12.2

9.0

`rgb_functional_notation`

1

12

1

4

3.5

1

≤37

18

4

10.1

1

1.0

`rgb_hexadecimal_notation`

1

12

1

3

3.5

1

≤37

18

4

10.1

1

1.0

`space_separated_functional_notation`

65

79

52

No

52

12.1

65

65

52

47

12.2

9.0

`transparent`

1

12

3

9

10

3.1

37

18

4

10.1

2

1.0

## See also

- The [`opacity`](opacity) property lets you define transparency at the element level.
- Some common properties that use this data type: [`color`](color), [`background-color`](background-color), [`border-color`](border-color), [`box-shadow`](box-shadow), [`outline-color`](outline-color), [`text-shadow`](text-shadow)
- [Applying color to HTML elements using CSS](https://developer.mozilla.org/en-US/docs/Web/HTML/Applying_color)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/color_value" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/color_value</a>
