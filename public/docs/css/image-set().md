# image-set()

The `image-set()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](css_functions) notation is a method of letting the browser pick the most appropriate CSS image from a given set, primarily for high pixel density screens.

Resolution and bandwidth differ by device and network access. The `image-set()` function delivers the most appropriate image resolution for a user’s device, providing a set of image options — each with an associated resolution declaration — from which the browser picks the most appropriate for the device and settings. Resolution can be used as a proxy for filesize — a user agent on a slow mobile connection with a high-resolution screen may prefer to receive lower-resolution images rather than waiting for a higher resolution image to load.

`image-set()` allows the author to provide options rather than determining what each individual user needs.

## Syntax

    image-set() = image-set( <image-set-option># )
    where <image-set-option> = [ <image> | <string> ] <resolution> and
          <string> is an <url>

### Values

Most commonly you'll see an `url()` `<string>` value, but the `<image>` can be any image type except for an image set. The `image-set()` function can not be nested inside another `image-set()` function.

`<resolution>` units include `x` or `dppx`, for dots per pixel unit, `dpi`, for dots per inch, and `dpcm` for dots per centimeter. Every image within an `image-set()` must have a unique resolution.

## Examples

### Using image-set() to provide alternative background-image options

This example shows how to use `image-set()` to provide two alternative [`background-image`](background-image) options, chosen depending on the resolution needed: a normal version and a high-resolution version.

## Accessibility concerns

Browsers do not provide any special information on background images to assistive technology. This is important primarily for screen readers, as a screen reader will not announce its presence and therefore convey nothing to its users. If the image contains information critical to understanding the page's overall purpose, it is better to describe it semantically in the document.

- [MDN Understanding WCAG, Guideline 1.1 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.1_%e2%80%94_providing_text_alternatives_for_non-text_content)
- [Understanding Success Criterion 1.1.1 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/2016/NOTE-UNDERSTANDING-WCAG20-20161007/text-equiv-all.html)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-images-4/#image-set-notation">CSS Images Module Level 4<br />
<span class="small">The definition of 'The image-set() notation' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`image-set()`

21

79

88

\["The `type()` function is not supported as an argument to `image-set()`. See [bug 1695404](https://bugzil.la/1695404).", "In `cursor` and `content` properties, gradients are not supported as arguments to `image-set()`. See [bug 1696314](https://bugzil.la/1696314)."\]

No

15

6

Support for `url` images only and `x` is the only supported resolution unit. See [bug 160934](https://webkit.org/b/160934).

4.4

25

88

\["The `type()` function is not supported as an argument to `image-set()`. See [bug 1695404](https://bugzil.la/1695404).", "In `cursor` and `content` properties, gradients are not supported as arguments to `image-set()`. See [bug 1696314](https://bugzil.la/1696314)."\]

14

6

Support for `url` images only and `x` is the only supported resolution unit. See [bug 160934](https://webkit.org/b/160934).

1.5

## See also

- [`<image>`](image)
- [`image()`](<image()>)
- [`element()`](<element()>)
- [`url()`](<url()>)
- [`<gradient>`](gradient)
- [`cross-fade()`](<cross-fade()>)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/image-set()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/image-set()</a>
