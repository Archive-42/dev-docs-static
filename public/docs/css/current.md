# :current

The `:current` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) selector is a time-dimensional pseudo-class that represents the element, or an ancestor of the element, that is currently being displayed. For example in a video with captions which are being displayed by [WebVTT](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API).

    :current(p, span) {
      background-color: yellow;
    }

## Syntax

    :current

## Examples

### CSS

    :current(p, span) {
      background-color: yellow;
    }

### HTML

    <video controls preload="metadata">
      <source src="video.mp4" type="video/mp4" />
      <source src="video.webm" type="video/webm" />
      <track label="English" kind="subtitles" srclang="en" src="subtitles.vtt" default>
    </video>

### WebVTT

    WEBVTT FILE

    1
    00:00:03.500 --> 00:00:05.000
    This is the first caption

    2
    00:00:06.000 --> 00:00:09.000
    This is the second caption

    3
    00:00:11.000 --> 00:00:19.000
    This is the third caption

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#the-current-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':current' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `css.selectors.current`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

The compatibility table in this page is generated from structured data. If you'd like to contribute to the data, please check out <https://github.com/mdn/browser-compat-data> and send us a pull request.

## See also

- [Web Video Text Tracks Format (WebVTT](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API))
- [`:past`](:past)
- [`:future`](:future)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:current" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:current</a>
