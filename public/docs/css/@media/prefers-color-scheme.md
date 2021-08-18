# prefers-color-scheme

The `prefers-color-scheme` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) is used to detect if the user has requested a light or dark color theme.

The user might indicate this preference through an operating system setting (e.g. light or dark mode) or a user agent setting.

## Syntax

`light`  
Indicates that user has notified that they prefer an interface that has a light theme, or has not expressed an active preference.

`dark`  
Indicates that user has notified that they prefer an interface that has a dark theme.

## Examples

The elements below have an initial color theme. They can be further themed according to the user's color scheme preference.

### HTML

    <div class="day">Day (initial)</div>
    <div class="day light-scheme">Day (changes in light scheme)</div>
    <div class="day dark-scheme">Day (changes in dark scheme)</div> <br>

    <div class="night">Night (initial)</div>
    <div class="night light-scheme">Night (changes in light scheme)</div>
    <div class="night dark-scheme">Night (changes in dark scheme)</div>

### CSS

    .day   { background: #eee; color: black; }
    .night { background: #333; color: white; }

    @media (prefers-color-scheme: dark) {
      .day.dark-scheme   { background:  #333; color: white; }
      .night.dark-scheme { background: black; color:  #ddd; }
    }

    @media (prefers-color-scheme: light) {
      .day.light-scheme   { background: white; color:  #555; }
      .night.light-scheme { background:  #eee; color: black; }
    }

    .day, .night {
      display: inline-block;
      padding: 1em;
      width: 7em;
      height: 2em;
      vertical-align: middle;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-5/#descdef-media-prefers-color-scheme">Media Queries Level 5<br />
<span class="small">The definition of 'prefers-color-scheme' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`prefers-color-scheme`

76

79

67

No

62

12.1

76

76

67

54

13

14.2

`no-preference`

76-80

79-80

67-79

No

62-71

12.1

76-80

76-80

67-79

54

13

14.2

## See also

- [Simulate prefers-color-scheme in Firefox](https://developer.mozilla.org/en-US/docs/Tools/Page_Inspector/How_to/Examine_and_edit_CSS#view_media_rules_for_prefers-color-scheme) (Firefox Page Inspector &gt; Examine and edit CSS)
- [Video tutorial: Coding a Dark Mode for your Website](https://www.youtube.com/watch?v=jmepqJ5UbuM)
- [Redesigning your product and website for dark mode](https://stuffandnonsense.co.uk/blog/redesigning-your-product-and-website-for-dark-mode)
- Changing color schemes in [Windows](https://blogs.windows.com/windowsexperience/2019/04/01/windows-10-tip-dark-theme-in-file-explorer/), [macOS](https://developer.apple.com/design/human-interface-guidelines/macos/visual-design/dark-mode/), [Android](https://www.theverge.com/2019/5/7/18530599/google-android-q-features-hands-on-dark-mode-gestures-accessibility-io-2019), or [other platforms](https://support.mozilla.org/en-US/questions/1271928).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-color-scheme" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-color-scheme</a>
