# prefers-contrast

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `prefers-contrast` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) is used to detect if the user has requested that the web content is presented with a higher (or lower) contrast.

## Syntax

`no-preference`  
Indicates that the user has made no preference known to the system. This keyword value evaluates as false in a Boolean context.

`more`  
Indicates that user has notified the system that they prefer an interface that has a higher level of contrast.

`less`  
Indicates that user has notified the system that they prefer an interface that has a lower level of contrast.

## User preferences

Various operating systems do support such preferences and user agents are likely to rely on the settings provided by the operating system.

## Examples

This example has an annoying low contrast by default.

### HTML

    <div class="contrast">low contrast box</div>

### CSS

    .contrast {
      width: 100px;
      height: 100px;
      outline: 2px dashed black;
    }

    @media (prefers-contrast: high) {
      .contrast {
        outline: 2px solid black;
      }
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-5/#descdef-media-prefers-contrast">Media Queries Level 5<br />
<span class="small">The definition of 'prefers-contrast' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`prefers-contrast`

No

No

80

No

No

No

No

No

No

No

No

No

## See also

- Microsoft [-ms-high-contrast](https://msdn.microsoft.com/library/Hh771830) media feature
- CSS [forced-colors](forced-colors) media query

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-contrast" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-contrast</a>
