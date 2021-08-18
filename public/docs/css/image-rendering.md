# image-rendering

The `image-rendering` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets an image scaling algorithm. The property applies to an element itself, to any images set in its other properties, and to its descendants.

The [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) will scale an image when the page author specifies dimensions other than its natural size. Scaling may also occur due to user interaction (zooming). For example, if the natural size of an image is `100×100px`_,_ but its actual dimensions are `200×200px` (or `50×50px`), then the image will be upscaled (or downscaled) using the algorithm specified by `image-rendering`. This property has no effect on non-scaled images.

## Syntax

    /* Keyword values */
    image-rendering: auto;
    image-rendering: crisp-edges;
    image-rendering: pixelated;

    /* Global values */
    image-rendering: inherit;
    image-rendering: initial;
    image-rendering: unset;

### Values

`auto`  
The scaling algorithm is UA dependent. Since version 1.9 (Firefox 3.0), Gecko uses _bilinear_ resampling (high quality).

`smooth` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The image should be scaled with an algorithm that maximizes the appearance of the image. In particular, scaling algorithms that "smooth" colors are acceptable, such as bilinear interpolation. This is intended for images such as photos.

`high-quality` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Identical to `smooth`, but with a preference for higher-quality scaling. If system resources are constrained, images with `high-quality` should be prioritized over those with any other value, when considering which images to degrade the quality of and to what degree.

`crisp-edges`  
The image must be scaled with an algorithm that preserves contrast and edges in the image, and which does not smooth colors or introduce blur to the image in the process. Suitable algorithms include nearest-neighbor and [other non-smoothing scaling algorithms](https://en.wikipedia.org/wiki/Pixel-art_scaling_algorithms) such as 2×SaI and [hqx-family](https://en.wikipedia.org/wiki/Hqx) algorithms. This value is intended for pixel-art images, such as in browser games.

`pixelated`  
When scaling the image up, the nearest-neighbor algorithm must be used, so that the image appears to be composed of large pixels. When scaling down, this is the same as `auto`.

**Note:** The values `optimizeQuality` and `optimizeSpeed` present in an early draft (and coming from its SVG counterpart `image-rendering`) are defined as synonyms for the `smooth` and `pixelated` values respectively.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | crisp-edges | pixelated

## Examples

### Setting image scaling algorithms

In practical use, the `pixelated` and `crisp-edges` rules can be combined to provide some fallback for each other. (Just prepend the actual rules with the fallback.) The [Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API) can provide a [fallback solution for `pixelated`](http://phrogz.net/tmp/canvas_image_zoom.html) through manual image data manipulation or with `imageSmoothingEnabled`.

#### CSS

    .auto {
      image-rendering: auto;
    }

    .pixelated {
      -ms-interpolation-mode: nearest-neighbor;
      image-rendering: pixelated;
    }

    .crisp-edges {
      image-rendering: -webkit-optimize-contrast;
      image-rendering: crisp-edges;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-images-3/#the-image-rendering">CSS Images Module Level 3<br />
<span class="small">The definition of 'image-rendering' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`image-rendering`

13

79

3.6

No

15

6

≤37

18

4

14

6

1.0

`crisp-edges`

13

79

65

3.6

No

15

6

≤37

18

65

4

14

6

1.0

`optimizeQuality`

28

79

3.6

No

15

6.1

≤37

28

4

14

7

1.5

`optimizeSpeed`

28

79

3.6

No

15

6.1

≤37

28

4

14

7

1.5

`pixelated`

41

79

No

No

26

10

41

41

No

26

10

4.0

**Note:** Although `crisp-edges` is supposed to use a pixel-art scaler like in the specification example, in practice no browsers (as of January 2020) does so. [In Firefox](https://dxr.mozilla.org/mozilla-central/rev/5fd4cfacc90ddd975c82ba27fdc56f4187b3f180/gfx/wr/webrender/src/resource_cache.rs#1727), `crisp-edges` is interpreted as nearest-neighbor, `pixelated` is not supported, and `auto` is interpolated as trilinear or linear.

For behavior on Chromium and Safari (WebKit), see the `GetInterpolationQuality` function and `CSSPrimitiveValue::operator ImageRendering()` respectively.

## See also

- Other image-related CSS properties: [`object-fit`](object-fit), [`object-position`](object-position), [`image-orientation`](image-orientation), [`image-rendering`](image-rendering), [`image-resolution`](image-resolution).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/image-rendering" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/image-rendering</a>
