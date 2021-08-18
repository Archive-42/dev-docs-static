# &lt;resolution&gt;

The `<resolution>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types), used for describing [resolutions](@media/resolution) in [media queries](media_queries), denotes the pixel density of an output device, i.e., its resolution.

On screens, the units are related to _CSS_ inches, centimeters, or pixels, not physical values.

## Syntax

The `<resolution>` data type consists of a strictly positive [`<number>`](number) followed by one of the units listed below. As with all CSS dimensions, there is no space between the unit literal and the number.

### Units

`dpi`  
Represents the number of [dots per inch](https://en.wikipedia.org/wiki/Dots_per_inch). Screens typically contains 72 or 96 dots per inch, but the dpi for printed documents is usually much greater. As 1 inch is 2.54 cm, `1dpi ≈ 0.39dpcm`.

`dpcm`  
Represents the number of [dots per centimeter](https://en.wikipedia.org/wiki/Dots_per_inch). As 1 inch is 2.54 cm, `1dpcm ≈ 2.54dpi`.

`dppx`  
Represents the number of dots per `px` unit. Due to the 1:96 fixed ratio of CSS `in` to CSS `px`, `1dppx` is equivalent to `96dpi`, which corresponds to the default resolution of images displayed in CSS as defined by [`image-resolution`](image-resolution).

`x`  
Alias for `dppx`.

**Note:** Although the number `0` is always the same regardless of unit, the unit may not be omitted. In other words, `0` is invalid and does not represent `0dpi`, `0dpcm`, or `0dppx`.

## Examples

### Use in a media query

    @media print and (min-resolution: 300dpi) { ... }

### Valid resolutions

    96dpi
    50.82dpcm
    3dppx

### Invalid resolutions

    72 dpi     Spaces are not allowed between the number and the unit.
    ten dpi    The number must use digits only.
    0          The unit is required.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-values-4/#resolution">CSS Values and Units Module Level 4<br />
<span class="small">The definition of '&lt;resolution&gt;' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Adds the <code>x</code> unit.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-values-3/#resolution">CSS Values and Units Module Level 3<br />
<span class="small">The definition of '&lt;resolution&gt;' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Adds the <code>dppx</code> unit.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-3/#resolution">Media Queries<br />
<span class="small">The definition of '&lt;resolution&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`resolution`

29

12

8

3.5

Supports [`<integer>`](https://developer.mozilla.org/docs/Web/CSS/integer) values only.

9

9.5

No

See [bug 78087](https://webkit.org/b/78087).

≤37

29

8

4

Supports [`<integer>`](https://developer.mozilla.org/docs/Web/CSS/integer) values only.

10.1

No

See [bug 78087](https://webkit.org/b/78087).

2.0

`dpcm`

29

12

8

9

16

10-15

No

≤37

29

8

16

10.1-14

No

2.0

`dpi`

29

12

8

9

16

10-15

No

≤37

29

8

16

10.1-14

No

2.0

`dppx`

29

12

16

No

12.1

No

≤37

29

16

12.1

No

2.0

`x`

68

79

62

No

55

No

68

68

62

48

No

10.0

## See also

- [resolution](@media/resolution) media feature
- The [`image-resolution`](image-resolution) property
- [Using @media queries](media_queries/using_media_queries)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/resolution" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/resolution</a>
