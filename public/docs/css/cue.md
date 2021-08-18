# ::cue

The `::cue` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-element](pseudo-elements) matches [WebVTT](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API) cues within a selected element. This can be used to [style captions and other cues](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API#styling_webtt_cues) in media with VTT tracks.

    ::cue {
      color: yellow;
      font-weight: bold;
    }

The properties are applied to the entire set of cues as if they were a single unit. The only exception is that `background` and its longhand properties apply to each cue individually, to avoid creating boxes and obscuring unexpectedly large areas of the media.

## Syntax

    ::cue | ::cue( <selector> )

## Permitted properties

Rules whose selectors include this element may only use the following CSS properties:

- [`background`](background)
- [`background-attachment`](background-attachment)
- [`background-clip`](background-clip)
- [`background-color`](background-color)
- [`background-image`](background-image)
- [`background-origin`](background-origin)
- [`background-position`](background-position)
- [`background-repeat`](background-repeat)
- [`background-size`](background-size)
- [`color`](color)
- [`font`](font)
- [`font-family`](font-family)
- [`font-size`](font-size)
- [`font-stretch`](font-stretch)
- [`font-style`](font-style)
- [`font-variant`](font-variant)
- [`font-weight`](font-weight)
- [`line-height`](line-height)
- [`opacity`](opacity)
- [`outline`](outline)
- [`outline-color`](outline-color)
- [`outline-style`](outline-style)
- [`outline-width`](outline-width)
- [`ruby-position`](ruby-position)
- [`text-combine-upright`](text-combine-upright)
- [`text-decoration`](text-decoration)
- [`text-decoration-color`](text-decoration-color)
- [`text-decoration-line`](text-decoration-line)
- [`text-decoration-style`](text-decoration-style)
- [`text-decoration-thickness`](text-decoration-thickness)
- [`text-shadow`](text-shadow)
- [`visibility`](visibility)
- [`white-space`](white-space)

## Examples

### Styling WebVTT cues as white-on-black

The following CSS sets the cue style so that the text is white and the background is a translucent black box.

    ::cue {
      color: #fff;
      background-color: rgba(0, 0, 0, 0.6);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webvtt/#the-cue-pseudo-element">WebVTT: The Web Video Text Tracks Format<br />
<span class="small">The definition of '::cue' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`::cue`

26

79

55

From Firefox 69, only allowed properties apply to the `::cue` pseudo-element with no argument. See [Permitted properties](https://developer.mozilla.org/docs/Web/CSS/::cue#Permitted_properties) for a list of the allowed properties.

No

15

6.1

≤37

26

55

14

6.1

1.5

`selector_argument`

26

79

No

No

15

6.1

≤37

26

No

14

6.1

1.5

## See also

- [Web Video Tracks Format (WebVTT)](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API)
- [`<track>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track), [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/::cue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/::cue</a>
