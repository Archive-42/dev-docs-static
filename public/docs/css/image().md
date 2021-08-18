# image()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `image()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](css_functions) defines an [`<image>`](image) in a similar fashion to the [`<url>()`](<url()>) function, but with added functionality including specifying the image's directionality, specifying fallback images for when the preferred image is not supported, displaying just a part of that image defined by a media fragment, and specifying a solid color as a fallback in case none of the specified images are able to be rendered.

**Disambiguation:** [`Image()`, the `HTMLImageElement` constructor](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/Image).

## Syntax

    image( <image-tags>? [ <image-src>? , <color>? ]! )where
    <image-tags> = ltr | rtl
    <image-src> = <url> | <string>
    <color> = <rgb()> | <rgba()> | <hsl()> | <hsla()> | <hex-color> | <named-color> | currentcolor | <deprecated-system-color>where
    <rgb()> = rgb( <percentage>{3} [ / <alpha-value> ]? ) | rgb( <number>{3} [ / <alpha-value> ]? ) | rgb( <percentage>#{3} , <alpha-value>? ) | rgb( <number>#{3} , <alpha-value>? )
    <rgba()> = rgba( <percentage>{3} [ / <alpha-value> ]? ) | rgba( <number>{3} [ / <alpha-value> ]? ) | rgba( <percentage>#{3} , <alpha-value>? ) | rgba( <number>#{3} , <alpha-value>? )
    <hsl()> = hsl( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsl( <hue>, <percentage>, <percentage>, <alpha-value>? )
    <hsla()> = hsla( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsla( <hue>, <percentage>, <percentage>, <alpha-value>? )where
    <alpha-value> = <number> | <percentage>
    <hue> = <number> | <angle>

where:

`image-tags`<span class="badge inline optional">Optional</span>  
The directionality of the image, either `ltr` for left-to-right or `rtl` for right-to-left.

`image-src` <span class="badge inline optional">Optional</span>  
Zero or more [`<url>()`](<url()>)s or [`<string>`](string)s specifying the image sources, with optional image fragment identifiers.

`color`<span class="badge inline optional">Optional</span>  
A color, specifying a solid background color to use as a fallback if no `image-src` is found, supported, or declared.

### Bi-directional awareness

The first, optional parameter of the `image()` notation is the directionality of the image. If included, and the image is used on an element with opposite directionality, the image will be flipped horizontally in horizontal writing modes. If the directionality is omitted, the image won't be flipped if the language direction is changed.

### Image fragments

One key difference between `url()` and `image()` is the ability to add a media fragment identifier — a starting point along the x and y axis, along with a width and height — onto the image source to display only a section of the source image. The section of the image defined in the parameter becomes a standalone image. The syntax looks like so:

    background-image: image('myimage.webp#xywh=0,20,40,60');

The background image of the element will be the portion of the image _myImage.webp_ that starts at the coordinate 0px, 20px (the top left hand corner) and is 40px wide and 60px tall.

The `#xywh=#,#,#,#` media fragment syntax takes four comma separated numeric values. The first two represent the X and Y coordinates for the starting point of the box that will be created. The third value is the width of the box, and the last value is the height. By default, these are pixel values. The [spacial dimension definition in the media specification](https://www.w3.org/TR/media-frags/#naming-space) indicates that percentages will be supported as well:

    xywh=160,120,320,240        /* results in a 320x240 image at x=160 and y=120 */
    xywh=pixel:160,120,320,240  /* results in a 320x240 image at x=160 and y=120 */
    xywh=percent:25,25,50,50    /* results in a 50%x50% image at x=25% and y=25% */

The image fragments can be used in `url()` notation as well. The `#xywh=#,#,#,#` media fragment syntax is 'backwards compatible' in that a media fragment will be ignored if not understood, and won't break the source call when used with `url()`. If the browser doesn't understand the media fragments notation, it ignores the fragment, displaying the entire image.

Browsers that understand `image()` also understand the fragment notation. Therefore, if the fragment is not understood within `image()`, the image will be considered invalid.

### Color fallback

If a color is specified in `image()` along with your image sources, it acts as a fallback if the images are invalid and do not appear. In such cases, the `image()` function renders as if no image were included, generating a solid-color image. As a use case, consider a dark image being used as a background for some white text. A dark background color may be needed for foreground text to be legible, if the image does not render.

Omitting image sources while including a color is valid and creates a color swatch. Unlike declaring a [`background-color`](background-color), which is placed under or behind all the background images, this can be used to put (generally semi-transparent) colors over other images.

The size of the color swatch can be set with the [`background-size`](background-size) property. This is different from the `background-color`, which sets a color to cover the entire element. Both `image(color)` and `background-color` placements are impacted by the [`background-clip`](background-clip) and [`background-origin`](background-origin) properties.

## Accessibility concerns

Browsers do not provide any special information on background images to assistive technology. This is important primarily for screen readers, as a screen reader will not announce its presence and therefore convey nothing to its users. If the image contains information critical to understanding the page's overall purpose, it is better to describe it semantically in the document.

- [MDN Understanding WCAG, Guideline 1.1 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.1_%e2%80%94_providing_text_alternatives_for_non-text_content)
- [Understanding Success Criterion 1.1.1 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/2016/NOTE-UNDERSTANDING-WCAG20-20161007/text-equiv-all.html)

This feature can help improve accessibility by providing a fallback color when an image fails to load. While this can and should be done by including a background-color on every background image, the CSS `image()` function allows adding allows only including background colors should an image fail to load, which means you can add a fall back color should a transparent PNG/GIF/WebP not load.

## Examples

### Directionally-sensitive images

    <ul>
      <li dir="ltr">Bullet is a right facing arrow on the left</li>
      <li dir="rtl">Bullet is the same arrow, flipped to point left.</li>
    </ul>

    ul {
      list-style-image: image(ltr 'https://mdn.mozillademos.org/files/16412/rightarrow.png');
    }

In the left-to-right list items — those with `dir="ltr"` set on the element itself or inheriting the directionality from an ancestor or default value for the page — the image will be used as-is. List items with `dir="rtl"` set on the `<li>` or inheriting the right-to-left directionality from an ancestor, such as documents set to Arabic or Hebrew, will have the bullet display on the right, horizontally flipped, as if `transform: scalex(-1)` had been set. The text will also be displayed left-to-right.

### Displaying a section of the background image

    <div class="box">Hover over me. What cursor do you see?</div>

    .box:hover {
      cursor: image("https://mdn.mozillademos.org/files/16411/sprite.png#xywh=32,64,16,16");
    }

When the user hovers over the box, the cursor will change to display the 16x16 px section of the sprite image, starting at x=32 and y=64.

### Providing fallback images

    .help::before {
      content: image("try.webp", "try.svg", "try.gif");
    }

In this example, the browser will display an image as generated content before the content of the element with the class of `help`. The image displayed will be a WebP image, if WebP is supported. If not, the SVG example will be shown. If SVG is not supported, the GIF version will display.

### Putting color on top of a background image

    .quarterlogo {
      background-image:
        image(rgba(0, 0, 0, 0.25)),
        url("https://mdn.mozillademos.org/files/12053/firefox.png");
      background-size: 25%;
      background-repeat: no-repeat;
    }

    <div class="quarterlogo">If supported, a quarter of this div has a darkened logo</div>

The above will put a semi-transparent black mask over the Firefox logo background image. Had we used the [`background-color`](background-color) property instead, the color would have appeared behind the logo image instead of on top of it. Additionally, the entire container would have had the same background color. Because we used `image()` along with the [`background-size`](background-size) property (and prevented the image from repeating with the [`background-repeat`](background-repeat) property, the color swatch will only cover a quarter of the container.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-images-4/#image-notation">CSS Images Module Level 4<br />
<span class="small">The definition of 'image()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`image()`

No

No

No

\["See [bug 703217](https://bugzil.la/703217).", "The [`-moz-image-rect()`](https://developer.mozilla.org/docs/Web/CSS/-moz-image-rect) function supports fragments as of Firefox 4."\]

No

No

No

No

No

No

The [`-moz-image-rect()`](https://developer.mozilla.org/docs/Web/CSS/-moz-image-rect) function supports fragments as of Firefox 4.

No

No

No

## See also

- [`<image>`](image)
- [`element()`](<element()>)
- [`<url>()`](<url()>)
- [`clip-path`](clip-path)
- [`-moz-image-rect()`](-moz-image-rect)
- [`<gradient>`](gradient)
- [`image-set()`](<image-set()>)
- [`cross-fade()`](<cross-fade()>)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/image()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/image()</a>
