# &lt;blend-mode&gt;

The `<blend-mode>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types) describes how colors should appear when elements overlap. It is used in the [`background-blend-mode`](background-blend-mode) and [`mix-blend-mode`](mix-blend-mode) properties.

## Syntax

The `<blend-mode>` data type is defined using a keyword value chosen from the list below.

### Values

`normal`  
The final color is the top color, regardless of what the bottom color is.  
The effect is like two opaque pieces of paper overlapping.

`multiply`  
The final color is the result of multiplying the top and bottom colors.  
A black layer leads to a black final layer, and a white layer leads to no change.  
The effect is like two images printed on transparent film overlapping.

`screen`  
The final color is the result of inverting the colors, multiplying them, and inverting that value.  
A black layer leads to no change, and a white layer leads to a white final layer.  
The effect is like two images shone onto a projection screen.

`overlay`  
The final color is the result of `multiply` if the bottom color is darker, or `screen` if the bottom color is lighter.  
This blend mode is equivalent to `hard-light` but with the layers swapped.

`darken`  
The final color is composed of the darkest values of each color channel.

`lighten`  
The final color is composed of the lightest values of each color channel.

`color-dodge`  
The final color is the result of dividing the bottom color by the inverse of the top color.  
A black foreground leads to no change. A foreground with the inverse color of the backdrop leads to a fully lit color.  
This blend mode is similar to `screen`, but the foreground need only be as light as the inverse of the backdrop to create a fully lit color.

`color-burn`  
The final color is the result of inverting the bottom color, dividing the value by the top color, and inverting that value.  
A white foreground leads to no change. A foreground with the inverse color of the backdrop leads to a black final image.  
This blend mode is similar to `multiply`, but the foreground need only be as dark as the inverse of the backdrop to make the final image black.

`hard-light`  
The final color is the result of `multiply` if the top color is darker, or `screen` if the top color is lighter.  
This blend mode is equivalent to `overlay` but with the layers swapped.  
The effect is similar to shining a _harsh_ spotlight on the backdrop.

`soft-light`  
The final color is similar to `hard-light`, but softer.  
This blend mode behaves similar to `hard-light`.  
The effect is similar to shining a _diffused_ spotlight on the backdrop*.*

`difference`  
The final color is the result of subtracting the darker of the two colors from the lighter one.  
A black layer has no effect, while a white layer inverts the other layer's color.

`exclusion`  
The final color is similar to `difference`, but with less contrast.  
As with `difference`, a black layer has no effect, while a white layer inverts the other layer's color.

`hue`  
The final color has the _hue_ of the top color, while using the _saturation_ and _luminosity_ of the bottom color.

`saturation`  
The final color has the _saturation_ of the top color, while using the _hue_ and _luminosity_ of the bottom color.  
A pure gray backdrop, having no saturation, will have no effect.

`color`  
The final color has the _hue_ and _saturation_ of the top color, while using the _luminosity_ of the bottom color.  
The effect preserves gray levels and can be used to colorize the foreground.

`luminosity`  
The final color has the _luminosity_ of the top color, while using the _hue_ and _saturation_ of the bottom color.  
This blend mode is equivalent to `color`, but with the layers swapped.

## Description

For each pixel among the layers to which it is applied, a blend mode takes the colors of the foreground and the background, performs a calculation on them, and returns a new color value.

Changes between blend modes are not interpolated. Any change occurs immediately.

## Examples

### Blend mode comparison

In the following example, we have a `<div>` with two background images set on it — a Firefox logo on top of a linear gradient. Below it we have a provided a `<select>` menu that allows you to change the `background-blend-mode` applied to the `<div>`, allowing you to compare the different blend mode effects.

#### HTML

    <div></div>
    <p>Choose a blend-mode:</p>
    <select>
      <option selected>normal</option>
      <option>multiply</option>
      <option>screen</option>
      <option>overlay</option>
      <option>darken</option>
      <option>lighten</option>
      <option>color-dodge</option>
      <option>color-burn</option>
      <option>hard-light</option>
      <option>soft-light</option>
      <option>difference</option>
      <option>exclusion</option>
      <option>hue</option>
      <option>saturation</option>
      <option>color</option>
      <option>luminosity</option>
    </select>

#### CSS

    div {
      width: 300px;
      height: 300px;
      background: url(https://media.prod.mdn.mozit.cloud/attachments/2020/07/29/17350/3b4892b7e820122ac6dd7678891d4507/firefox.png) no-repeat center,
      linear-gradient(to bottom, blue, orange);
    }

#### JavaScript

    const selectElem = document.querySelector('select');
    const divElem = document.querySelector('div');

    selectElem.addEventListener('change', () => {
      divElem.style.backgroundBlendMode = selectElem.value;
    });

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/compositing-1/#ltblendmodegt">Compositing and Blending Level 1<br />
<span class="small">The definition of '&lt;blend-mode&gt;' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`blend-mode`

35

79

30

No

22

8

59

59

54

22

8

7.0

## See also

- Properties that use this data type: [`background-blend-mode`](background-blend-mode), [`mix-blend-mode`](mix-blend-mode)

Description to various blend modes on other website:

- [Blend modes](https://en.wikipedia.org/wiki/Blend_modes) on Wikipedia
- [Blending modes in Adobe Photoshop](https://helpx.adobe.com/photoshop/using/blending-modes.html) by Adobe

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/blend-mode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/blend-mode</a>
