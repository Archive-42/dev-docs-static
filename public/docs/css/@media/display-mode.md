# display-mode

The `display-mode` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) can be used to test the display mode of an application. You can use it to provide a consistent user experience between launching a site from a URL and launching it from a desktop icon.

This feature corresponds to the Web app manifest's [`display`](https://developer.mozilla.org/en-US/docs/Web/Manifest#display) member. Both apply to the top-level browsing context and any child browsing contexts. The feature query applies regardless of whether a web app manifest is present.

## Syntax

The `display-mode` feature is specified as a keyword value chosen from the list below.

<table><thead><tr class="header"><th>Display mode</th><th>Description</th><th>Fallback display mode</th></tr></thead><tbody><tr class="odd"><td><code>fullscreen</code></td><td>All of the available display area is used and no user agent <a href="https://developer.mozilla.org/en-US/docs/Glossary/Chrome">chrome</a> is shown.</td><td><code>standalone</code></td></tr><tr class="even"><td><code>standalone</code></td><td>The application will look and feel like a standalone application. This can include the application having a different window, its own icon in the application launcher, etc. In this mode, the user agent will exclude UI elements for controlling navigation, but can include other UI elements such as a status bar.</td><td><code>minimal-ui</code></td></tr><tr class="odd"><td><code>minimal-ui</code></td><td>The application will look and feel like a standalone application, but will have a minimal set of UI elements for controlling navigation. The elements will vary by browser.</td><td><code>browser</code></td></tr><tr class="even"><td><code>browser</code></td><td>The application opens in a conventional browser tab or new window, depending on the browser and platform.</td><td>(none)</td></tr></tbody></table>

## Examples

### The CSS is used if the device is at fullscreen

    @media all and (display-mode: fullscreen) {
      body {
        margin: 0;
        border: 5px solid black;
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/manifest/#the-display-mode-media-feature">Web App Manifest<br />
<span class="small">The definition of 'display-mode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`display-mode`

45

79

47

Firefox 47 and later support `display-mode` values `fullscreen` and `browser`. Firefox 57 added support for `minimal-ui` and `standalone` values.

No

32

13

45

45

47

Firefox 47 and later support `display-mode` values `fullscreen` and `browser`. Firefox 57 added support for `minimal-ui` and `standalone` values.

32

12.2

5.0

## See also

- [Using Media Queries](../media_queries/using_media_queries)
- [@media](../@media)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/display-mode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/display-mode</a>
