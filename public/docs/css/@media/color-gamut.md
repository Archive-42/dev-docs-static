# color-gamut

The `color-gamut` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) can be used to test the approximate range of colors that are supported by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) and the output device.

## Syntax

The `color-gamut` feature is specified as a keyword value chosen from the list below.

`srgb`  
The output device can support approximately the [sRGB](https://en.wikipedia.org/wiki/SRGB) gamut or more. This includes the vast majority of color displays.

`p3`  
The output device can support approximately the gamut specified by the [DCI P3 Color Space](https://en.wikipedia.org/wiki/DCI-P3) or more. The p3 gamut is larger than and includes the srgb gamut.

`rec2020`  
The output device can support approximately the gamut specified by the [ITU-R Recommendation BT.2020 Color Space](https://en.wikipedia.org/wiki/Rec._2020) or more. The rec2020 gamut is larger than and includes the p3 gamut.

## Examples

### HTML

    <p>This is a test.</p>

### CSS

    @media (color-gamut: srgb) {
      p {
        background: #f4ae8a;
      }
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-4/#color-gamut">Media Queries Level 4<br />
<span class="small">The definition of 'color-gamut' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`color-gamut`

58

79

No

No

45

10

58

58

No

43

10

7.0

## See also

- [Using Media Queries](../media_queries/using_media_queries)
- [@media](../@media)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/color-gamut" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/color-gamut</a>
