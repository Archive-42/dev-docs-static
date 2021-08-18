# -ms-high-contrast

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The **-ms-high-contrast** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) is a [Microsoft extension](https://developer.mozilla.org/en-US/docs/Web/CSS/Microsoft_Extensions) that describes whether the application is being displayed in high contrast mode, and with what color variation.

High Contrast Mode is a specialized display mode that prioritizes making content as legible as possible by dynamically replacing foreground and background colors with a user-specified theme. For web content, theme colors are mapped to content types.

This media feature applies to bitmap media types. It does not accept _min/max_ prefixes.

## Syntax

The `-ms-high-contrast` media feature is specified as one of the following values.

### Values

`none` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
...  
**No longer supported as of Microsoft Edge 18.**

`active`  
Indicates that the subsequent styling rules will be applied when the system is placed in high contrast mode with any color variation.

`black-on-white`  
Indicates that the subsequent styling rules will be applied when the system is placed in high contrast mode with a black-on-white color variation.

`white-on-black`  
Indicates that the subsequent styling rules will be applied when the system is placed in high contrast mode with a white-on-black color variation.

## Examples

### Matching any high-contrast variations

    @media screen and (-ms-high-contrast: active) {
      /* All high contrast styling rules */
    }

### Matching a black-on-white variation

    @media screen and (-ms-high-contrast: black-on-white) {
      div { background-image: url('image-bw.png'); }
    }

### Matching a white-on-black variation

    @media screen and (-ms-high-contrast: white-on-black) {
      div { background-image: url('image-wb.png'); }
    }

## Accessibility concerns

### Theming

High Contrast Mode's theme colors come from a limited subset of deprecated [CSS2 system colors](https://www.w3.org/TR/2018/REC-css-color-3-20180619/#css2-system). The available color keywords are:

- `windowText`: controls the color of text content.
- `highlightText`: controls the color of selected text.
- `highlight`: controls the background color of selected text.
- `buttonFace`: controls the color of a [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) element's text.
- `window`: controls the color of the background.
- The [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) element controls the color of links.

Because High Contrast Mode themes are dynamic, use these color keywords in place of other [CSS color values](../color). This will ensure that content will always be able to be perceived.

### Content

If at all possible, prefer updating HTML markup over modifying content using CSS2 system color keywords. This helps keep the content more predictable.

## Specifications

Not part of any standard.

## Remarks

As of Microsoft Edge 18, `-ms-high-contrast: none` is no longer supported. Microsoft Edge versions 18 and higher will be using the [`forced-colors` media feature](forced-colors) instead, but the `forced-colors` media feature specification is still being actively worked on.

The `-ms-high-contrast` media feature works with the <span class="page-not-created">`-ms-high-contrast-adjust`</span> property.

The `-ms-high-contrast` media feature was introduced in Windows 8.

## See also

- [Using Media Queries](../media_queries/using_media_queries)
- [@media](../@media)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/-ms-high-contrast" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/-ms-high-contrast</a>
