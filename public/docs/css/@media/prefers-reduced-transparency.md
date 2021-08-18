# prefers-reduced-transparency

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Draft**

This page is not complete.

The `prefers-reduced-transparency` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) is used to detect if the user has requested that the system minimize the amount of transparency used across elements.

## Syntax

`no-preference`  
Indicates that the user has made no preference known to the system. This keyword value evaluates as false in the boolean context.

`reduce`  
Indicates that user has notified the system that they prefer an interface that minimizes the amount of transparent or translucent layer effects.

## User preferences

Currently no user agent implements this feature, although various operating systems do support such preferences and if this media query is ever implemented user agents will likely rely on the settings provided by the operating systems.

## Examples

**Note:** No browser currently implements this feature so the following example will not work.

This example has an annoying transparency effect by default.

### HTML

    <div class="transparency">transparent box</div>

### CSS

    .transparency {
      opacity: 0.5;
    }

    @media (prefers-reduced-transparency: reduce) {
      .transparency {
        opacity: 1;
      }
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-5/#descdef-media-prefers-reduced-transparency">Media Queries Level 5<br />
<span class="small">The definition of 'prefers-reduced-transparency' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`prefers-reduced-transparency`

No

No

No

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

- [WebKit bug 175497](https://bugs.webkit.org/show_bug.cgi?id=175497)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-transparency" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-transparency</a>
