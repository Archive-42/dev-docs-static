# ::cue-region

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `::cue-region` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-element](pseudo-elements) matches [WebVTT](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API) cues within a selected element. This can be used to [style captions and other cues](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API#styling_webtt_cues) in media with VTT tracks.

    ::cue-region {
      color: yellow;
      font-weight: bold;
    }

The properties are applied to the entire set of cues as if they were a single unit. The only exception is that `background` and its shorthand properties apply to each cue individually, to avoid creating boxes and obscuring unexpectedly large areas of the media.

## Syntax

    ::cue-region | ::cue-region( <selector> )

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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webvtt/#the-cue-region-pseudo-element">WebVTT: The Web Video Text Tracks Format<br />
<span class="small">The definition of 'the <code>::cue-region</code> pseudo-element' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `css.selectors.cue-region`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- Other [WebVTT](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API) selectors:
  - [`::cue`](::cue)
  - [`:past`](:past)
  - [`:future`](:future)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/::cue-region" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/::cue-region</a>
