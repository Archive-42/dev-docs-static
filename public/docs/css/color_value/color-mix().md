# color-mix()

The `color-mix()` functional notation takes two [`color`](../color_value) values and returns the result of mixing them in a given colorspace by a given amount.

## Syntax

    color-mix(in lch, peru 40%, lightgoldenrod);
    color-mix(in srgb, #34c9eb 20%, white);

### Values

Functional notation: ` color-mix( in <colorspace> , [ <color> && <percentage>? ]#{2})`  
`<colorspace>` is one of `srgb`, `hsl`, `hwb`, `xyz`, `lab`, `lch`. If no colorspace is specified the default is `lch`.

`[ <color>` is any valid [`color`](../color_value).

`<percentage>` is the percentage of that color to mix.

## Examples

### HTML

    <ul>
      <li>10% #34c9eb</li>
      <li>40% #34c9eb</li>
      <li>70% #34c9eb</li>
    </ul>

### CSS

    li:nth-child(1) {
      background-color: color-mix(in srgb, #34c9eb 10%, white);
    }

    li:nth-child(2) {
      background-color: color-mix(in srgb, #34c9eb 40%, white);
    }

    li:nth-child(3) {
      background-color: color-mix(in srgb, #34c9eb 70%, white);
    }

#### Result

In a supporting browser the three items become more blue as a higher percentage of `#34c9eb` is mixed in.

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-color-5/#color-mix">CSS Color Module Level 5</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`color-mix()`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/color-mix()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/color-mix()</a>
