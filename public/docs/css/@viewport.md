# @viewport

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Note**: See <https://github.com/w3c/csswg-drafts/issues/4766> for discussion around @viewport's removal from the standards track.

The `@viewport` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [at-rule](at-rule) lets you configure the [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport) through which the document is viewed. It's primarily used for mobile devices, but is also used by desktop browsers that support features like "snap to edge" (such as Microsoft Edge).

Lengths specified as percentages are calculated relative to the **initial viewport**, which is the viewport before any user agent or authored styles have had an opportunity to adjust the viewport. This is typically based on the size of the window on desktop browsers that aren't in full screen mode.

On mobile devices (or desktop devices that are in full screen mode), the initial viewport is usually the portion of a device's screen that is available for application use. This may be either the full screen or the full screen area minus areas controlled by the operating system (such as a taskbar) or the application-available screen area (either the full screen or the screen minus any areas owned by the operating system or other applications).

    @viewport {
      width: 100vw; /*Sets the width of the actual viewport to the device width*/
    }

**Note**: The use of `<meta name="viewport">` tag overrides `@viewport`

## Syntax

The at-rule contains a set of nested [descriptor](<https://developer.mozilla.org/en-US/docs/Glossary/Descriptor_(CSS)>)s in a CSS block that is delimited by curly braces.

A _zoom factor_ of `1.0` or `100%` corresponds to no zooming. Larger values zoom in. Smaller values zoom out.

### Descriptors

Browser support for `@viewport` is weak at this time, with support being largely available in Internet Explorer and Edge. Even in those browsers, only a small number of descriptors are available. Browsers will ignore `@viewport` if they don't support it, and will ignore any descriptors that they don't recognize.

[`min-width`](@viewport)  
Used in the determination of the width of the viewport when the document is first displayed.

[`max-width`](@viewport)  
Used in the determination of the width of the viewport when the document is first displayed.

[`width`](@viewport)  
A shorthand descriptor for setting both `min-width` and `max-width`.

[`min-height`](@viewport)  
Used in the determination of the height of the viewport when the document is first displayed.

[`max-height`](@viewport)  
Used in the determination of the height of the viewport when the document is first displayed.

[`height`](@viewport)  
A shorthand descriptor for setting both `min-height` and `max-height`.

[`zoom`](@viewport)  
Sets the initial zoom factor.

[`min-zoom`](@viewport)  
Sets the minimum zoom factor.

[`max-zoom`](@viewport)  
Sets the maximum zoom factor.

[`user-zoom`](@viewport)  
Controls whether or not the user should be able to change the zoom factor.

[`orientation`](@viewport)  
Controls the document's orientation.

[`viewport-fit`](@viewport)  
Controls the display of the document on non-rectangular displays.

## Formal syntax

    @viewport {
      <group-rule-body>
    }

## Examples

### Setting viewport size, zoom, and orientation

    @viewport {
      min-width: 640px;
      max-width: 800px;
    }

    @viewport {
      zoom: 0.75;
      min-zoom: 0.5;
      max-zoom: 0.9;
    }

    @viewport {
      orientation: landscape;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-round-display/#extending-viewport-rule">CSS Round Display Level 1<br />
<span class="small">The definition of '@viewport' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Defined the <a href="@viewport"><code>viewport-fit</code></a> descriptor.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-device-adapt/#atviewport-rule">CSS Device Adaptation<br />
<span class="small">The definition of '@viewport' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`@viewport`

29-84

See Chromium [bug 235457](https://crbug.com/235457).

12

No

See Firefox [bug 747754](https://bugzil.la/747754).

10

16

11.1-15

No

See WebKit [bug 95959](https://webkit.org/b/95959).

4.4-37

29-84

See Chromium [bug 235457](https://crbug.com/235457).

No

See Firefox [bug 747754](https://bugzil.la/747754).

16

11.1-14

No

See WebKit [bug 95959](https://webkit.org/b/95959).

2.0

## See also

- [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta), specifically `<meta name="viewport">`
- [Using the viewport meta tag to control layout on mobile browsers](https://developer.mozilla.org/en-US/docs/Web/HTML/Viewport_meta_tag)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@viewport" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@viewport</a>
