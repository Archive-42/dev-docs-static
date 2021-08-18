# CSSMediaRule.media

The read-only `media` property of the [`CSSMediaRule`](../cssmediarule) interface [`MediaList`](../medialist) represents the intended destination medium for style information.

## Syntax

    var media = CSSMediaRule.media;

### Value

a [`MediaList`](../medialist)

## Examples

The CSS includes a media query with one style rule. This will be the first [`CSSRule`](../cssrule) returned by `document.styleSheets[0].cssRules`. Calling `myRules[0].media` therefore returns a [`MediaList`](../medialist) object representing the media query.

    @media (min-width: 500px) {
      body {
        color: blue;
      }
    }

    let myRules = document.styleSheets[0].cssRules;
    console.log(myRules[0].media); // a MediaList

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-conditional-3/#dom-cssmediarule-media">CSS Conditional Rules Module Level 3<br />
<span class="small">The definition of 'CSSMediaRule.media' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Make it derived from the <a href="../cssconditionrule"><code>CSSConditionRule</code></a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSMediaRule">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSMediaRule.media' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`media`

1

12

1

9

≤12.1

3

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSMediaRule/media" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSMediaRule/media</a>
