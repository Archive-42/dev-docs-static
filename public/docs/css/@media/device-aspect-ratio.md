# device-aspect-ratio

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `device-aspect-ratio` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) can be used to test the width-to-height aspect ratio of an output device.

## Syntax

The `device-aspect-ratio` feature is specified as a [`<ratio>`](../ratio). It is a range feature, meaning that you can also use the prefixed `min-device-aspect-ratio` and `max-device-aspect-ratio` variants to query minimum and maximum values, respectively.

## Examples

### Using min-device-aspect-ratio

    article {
      padding: 1rem;
    }

    @media screen and (min-device-aspect-ratio: 16/9) {
      article {
        padding: 1rem 5vw;
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-4/#device-aspect-ratio">Media Queries Level 4<br />
<span class="small">The definition of 'device-aspect-ratio' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Deprecated in Media Queries Level 4.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/mediaqueries-3/#device-aspect-ratio">Media Queries<br />
<span class="small">The definition of 'device-aspect-ratio' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`device-aspect-ratio`

1

12

2

9

10

3

≤37

18

4

10.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/device-aspect-ratio" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/device-aspect-ratio</a>
