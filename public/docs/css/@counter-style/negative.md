# negative

When defining custom counter styles, the `negative` descriptor lets you alter the representations of negative counter values, by providing a way to specify symbols to be appended or prepended to the counter representation when the value is negative.

## Syntax

    /* <symbol> values */
    negative: "-";       /* Prepends '-' if value is negative */
    negative: "(" ")";   /* Surrounds value by '(' and ')' if it is negative */

### Values

first `<symbol>`  
This symbol will be prepended to the representation when the counter is negative.

second `<symbol>`  
If present, this symbol will be appended to the representation when the counter is negative.

## Description

If the counter value is negative, the symbol provided as value for the descriptor is prepended to the counter representation; and a second symbol if specified, will be appended to the representation. The negative descriptor has effect only if the `system` value is `symbolic`, `alphabetic`, `numeric`, `additive`, or `extends`, if the extended counter style itself uses a negative sign. If the negative descriptor is specified for other systems that don't support negative counter values, then the descriptor is ignored.

## Formal definition

<table><tbody><tr class="odd"><td>Related <a href="../at-rule">at-rule</a></td><td><a href="../@counter-style"><code>@counter-style</code></a></td></tr><tr class="even"><td><a href="../initial_value">Initial value</a></td><td><code>"-" hyphen-minus</code></td></tr><tr class="odd"><td><a href="../computed_value">Computed value</a></td><td>as specified</td></tr></tbody></table>

## Formal syntax

    <symbol> <symbol>?where
    <symbol> = <string> | <image> | <custom-ident>where
    <image> = <url> | <image()> | <image-set()> | <element()> | <paint()> | <cross-fade()> | <gradient>where
    <image()> = image( <image-tags>? [ <image-src>? , <color>? ]! )
    <image-set()> = image-set( <image-set-option># )
    <element()> = element( <id-selector> )
    <paint()> = paint( <ident>, <declaration-value>? )
    <cross-fade()> = cross-fade( <cf-mixing-image> , <cf-final-image>? )
    <gradient> = <linear-gradient()> | <repeating-linear-gradient()> | <radial-gradient()> | <repeating-radial-gradient()> | <conic-gradient()>where
    <image-tags> = ltr | rtl
    <image-src> = <url> | <string>
    <color> = <rgb()> | <rgba()> | <hsl()> | <hsla()> | <hex-color> | <named-color> | currentcolor | <deprecated-system-color>
    <image-set-option> = [ <image> | <string> ] <resolution>
    <id-selector> = <hash-token>
    <cf-mixing-image> = <percentage>? && <image>
    <cf-final-image> = <image> | <color>
    <linear-gradient()> = linear-gradient( [ <angle> | to <side-or-corner> ]? , <color-stop-list> )
    <repeating-linear-gradient()> = repeating-linear-gradient( [ <angle> | to <side-or-corner> ]? , <color-stop-list> )
    <radial-gradient()> = radial-gradient( [ <ending-shape> || <size> ]? [ at <position> ]? , <color-stop-list> )
    <repeating-radial-gradient()> = repeating-radial-gradient( [ <ending-shape> || <size> ]? [ at <position> ]? , <color-stop-list> )
    <conic-gradient()> = conic-gradient( [ from <angle> ]? [ at <position> ]?, <angular-color-stop-list> )where
    <rgb()> = rgb( <percentage>{3} [ / <alpha-value> ]? ) | rgb( <number>{3} [ / <alpha-value> ]? ) | rgb( <percentage>#{3} , <alpha-value>? ) | rgb( <number>#{3} , <alpha-value>? )
    <rgba()> = rgba( <percentage>{3} [ / <alpha-value> ]? ) | rgba( <number>{3} [ / <alpha-value> ]? ) | rgba( <percentage>#{3} , <alpha-value>? ) | rgba( <number>#{3} , <alpha-value>? )
    <hsl()> = hsl( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsl( <hue>, <percentage>, <percentage>, <alpha-value>? )
    <hsla()> = hsla( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsla( <hue>, <percentage>, <percentage>, <alpha-value>? )
    <side-or-corner> = [ left | right ] || [ top | bottom ]
    <color-stop-list> = [ <linear-color-stop> [, <linear-color-hint>]? ]# , <linear-color-stop>
    <ending-shape> = circle | ellipse
    <size> = closest-side | farthest-side | closest-corner | farthest-corner | <length> | <length-percentage>{2}
    <position> = [ [ left | center | right ] || [ top | center | bottom ] | [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ]? | [ [ left | right ] <length-percentage> ] && [ [ top | bottom ] <length-percentage> ] ]
    <angular-color-stop-list> = [ <angular-color-stop> [, <angular-color-hint>]? ]# , <angular-color-stop>where
    <alpha-value> = <number> | <percentage>
    <hue> = <number> | <angle>
    <linear-color-stop> = <color> <color-stop-length>?
    <linear-color-hint> = <length-percentage>
    <length-percentage> = <length> | <percentage>
    <angular-color-stop> = <color> && <color-stop-angle>?
    <angular-color-hint> = <angle-percentage>where
    <color-stop-length> = <length-percentage>{1,2}
    <color-stop-angle> = <angle-percentage>{1,2}
    <angle-percentage> = <angle> | <percentage>

## Examples

### Rendering negative counters

#### HTML

    <ul class="list" start="-3">
      <li>One</li>
      <li>Two</li>
      <li>Three</li>
      <li>Four</li>
      <li>Five</li>
    </ul>

#### CSS

    @counter-style neg {
      system: numeric;
      symbols: "0" "1" "2" "3" "4" "5" "6" "7" "8" "9";
      negative: "(-" ")";
    }

    .list {
      list-style: neg;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-counter-styles-3/#counter-style-system">CSS Counter Styles Level 3<br />
<span class="small">The definition of 'system' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`negative`

No

No

33

No

No

No

No

No

33

No

No

No

## See also

- [`list-style`](../list-style), [`list-style-image`](../list-style-image), [`list-style-position`](../list-style-position)
- [`symbols()`](<../symbols()>), the functional notation creating anonymous counter styles.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/negative" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/negative</a>
