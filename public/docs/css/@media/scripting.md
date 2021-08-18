# scripting

The `scripting` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) can be used to test whether scripting (such as JavaScript) is available.

## Syntax

The `scripting` feature is specified as a keyword value chosen from the list below.

`none`  
Scripting is completely unavailable on the current document.

`initial-only`  
Scripting is enabled during the initial page load, but not afterwards.

`enabled`  
Scripting is supported and active on the current document.

## Examples

### HTML

    <p class="script-none">You do not have scripting available. :-(</p>
    <p class="script-initial-only">Your scripting is only enabled during the initial page load. Weird.</p>
    <p class="script-enabled">You have scripting enabled! :-)</p>

### CSS

    p {
      color: lightgray;
    }

    @media (scripting: none) {
      .script-none {
         color: red;
      }
    }

    @media (scripting: initial-only) {
      .script-initial-only {
        color: red;
      }
    }

    @media (scripting: enabled) {
      .script-enabled {
        color: red;
      }
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-5/#scripting">Media Queries Level 5<br />
<span class="small">The definition of 'scripting' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`scripting`

No

See [bug 489957](https://crbug.com/489957).

No

See [bug 489957](https://crbug.com/489957).

No

See [bug 1166581](https://bugzil.la/1166581).

No

No

No

No

See [bug 489957](https://crbug.com/489957).

No

See [bug 489957](https://crbug.com/489957).

No

See [bug 1166581](https://bugzil.la/1166581).

No

No

No

See [bug 489957](https://crbug.com/489957).

## See also

- [Using Media Queries](../media_queries/using_media_queries)
- [@media](../@media)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/scripting" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/scripting</a>
