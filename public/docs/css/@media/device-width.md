# device-width

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `device-width` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) can be used to test the width of an output device's rendering surface.

## Syntax

The `device-width` feature is specified as a [`<length>`](../length) value. It is a range feature, meaning that you can also use the prefixed `min-device-width` and `max-device-width` variants to query minimum and maximum values, respectively.

## Examples

### Applying a special stylesheet for devices that are narrower than 800 pixels

    <link rel="stylesheet" media="screen and (max-device-width: 799px)" href="http://foo.bar.com/narrow-styles.css" />

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-4/#device-width">Media Queries Level 4<br />
<span class="small">The definition of 'device-width' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Deprecated in Media Queries Level 4.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/mediaqueries-3/#device-width">Media Queries<br />
<span class="small">The definition of 'device-width' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`device-width`

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

## See also

- [Using Media Queries](../media_queries/using_media_queries)
- [@media](../@media)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/device-width" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/device-width</a>
