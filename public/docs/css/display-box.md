# &lt;display-box&gt;

These keywords define whether an element generates display boxes at all.

## Syntax

Valid `<display-box>` values:

`contents`  
These elements don't produce a specific box by themselves. They are replaced by their pseudo-box and their child boxes. Please note that the CSS Display Level 3 spec defines how the `contents` value should affect "unusual elements" — elements that aren’t rendered purely by CSS box concepts such as replaced elements. See [Appendix B: Effects of display: contents on Unusual Elements](https://drafts.csswg.org/css-display/#unbox) for more details.

_Due to a bug in browsers this will currently remove the element from the accessibility tree — screen readers will not look at what's inside. See the [Accessibility concerns](#accessibility_concerns) section below for more details._

`none`  
Turns off the display of an element so that it has no effect on layout (the document is rendered as though the element did not exist). All descendant elements also have their display turned off.  
To have an element take up the space that it would normally take, but without actually rendering anything, use the [`visibility`](visibility) property instead.

## Accessibility concerns

Current implementations in most browsers will remove from the [accessibility tree](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility#accessibility_apis) any element with a `display` value of `contents`. This will cause the element — and in some browser versions, its descendant elements — to no longer be announced by screen reading technology. This is incorrect behavior according to the [CSSWG specification](https://drafts.csswg.org/css-display/#the-display-properties).

- [More accessible markup with display: contents | Hidde de Vries](https://hiddedevries.nl/en/blog/2018-04-21-more-accessible-markup-with-display-contents)
- [Display: Contents Is Not a CSS Reset | Adrian Roselli](https://adrianroselli.com/2018/05/display-contents-is-not-a-css-reset.html)

## Examples

In this first example, the paragraph with a class of secret is set to `display: none`; the box and any content is now not rendered.

### display: none

#### HTML

    <p>Visible text</p>
    <p class="secret">Invisible text</p>

#### CSS

    p.secret {
      display: none;
    }

#### Result

### display: contents

In this example the outer [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) has a 2-pixel red border and a width of 300px. However it also has `display: contents` specified therefore this `<div>` will not be rendered, the border and width will no longer apply, and the child element will be displayed as if the parent had never existed.

#### HTML

    <div class="outer">
      <div>Inner div.</div>
    </div>

#### CSS

    .outer {
      border: 2px solid red;
      width: 300px;
      display: contents;
    }

    .outer > div {
      border: 1px solid green;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-display/#typedef-display-box">CSS Display Module Level 3<br />
<span class="small">The definition of 'display-box' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td></tr></tbody></table>

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

`display-box`

65

58-65

79

37

36-53

No

52

45-52

11.1

65

65

58-65

57

47

43-47

11.3

9.0

`contents_unusual`

58

79

59

No

45

No

65

58

59

43

No

9.0

BCD tables only load in the browser

## See also

- [`display`](display)
  - [`<display-outside>`](display-outside)
  - [`<display-inside>`](display-inside)
  - [`<display-listitem>`](display-listitem)
  - [`<display-internal>`](display-internal)
  - [`<display-legacy>`](display-legacy)
- [Display: Contents Is Not a CSS Reset | Adrian Roselli](https://adrianroselli.com/2018/05/display-contents-is-not-a-css-reset.html)
- [More accessible markup with display: contents — hiddedevries.nl](https://hiddedevries.nl/en/blog/2018-04-21-more-accessible-markup-with-display-contents)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/display-box" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/display-box</a>
