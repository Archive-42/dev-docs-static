# :any-link

The `:any-link` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) selector represents an element that acts as the source anchor of a hyperlink, independent of whether it has been visited. In other words, it matches every [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) or [`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area) element that has an `href` attribute. Thus, it matches all elements that match [`:link`](:link) or [`:visited`](:visited).

    /* Selects any element that would be matched by :link or :visited */
    :any-link {
      color: green;
    }

## Syntax

    :any-link

## Examples

### HTML

    <a href="https://example.com">External link</a><br>
    <a href="#">Internal target link</a><br>
    <a>Placeholder link (won't get styled)</a>

### CSS

    a:any-link {
      border: 1px solid blue;
      color: orange;
    }

    /* WebKit browsers */
    a:-webkit-any-link {
      border: 1px solid blue;
      color: orange;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#the-any-link-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':any-link' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:any-link`

65

1

79

79

50

1-50

No

52

15

9

3

1.2-3

65

≤37

65

18

50

4-50

47

14

9

1

9.0

1.0

`not_match_link`

65

79

87

No

52

No

Safari currently matches `<link>` elements with link pseudo-classes. See [Bug: 220740](https://webkit.org/b/220740).

65

65

87

47

No

Safari currently matches `<link>` elements with link pseudo-classes. See [Bug: 220740](https://webkit.org/b/220740).

9.0

## See also

- [Creating hyperlinks](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Creating_hyperlinks)
- Matches HTML elements: `<a>`, `<area>`, and `<link>` with an [`href`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#attr-href) attribute
- Related CSS selectors:
  - `:visited`
  - `:link`

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:any-link" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:any-link</a>
