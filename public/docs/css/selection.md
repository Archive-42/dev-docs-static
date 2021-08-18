# ::selection

The `::selection` CSS [pseudo-element](pseudo-elements) applies styles to the part of a document that has been highlighted by the user (such as clicking and dragging the mouse across text).

    ::selection {
      background-color: cyan;
    }

## Allowable properties

Only certain CSS properties can be used with `::selection`:

- [`color`](color)
- [`background-color`](background-color)
- [`text-decoration`](text-decoration) and its associated properties
- [`text-shadow`](text-shadow)
- <span class="page-not-created">`stroke-color`</span>, <span class="page-not-created">`fill-color`</span> and [`stroke-width`](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/stroke-width)

In particular, [`background-image`](background-image) is ignored.

## Syntax

    /* Legacy Firefox syntax (version 61 and below) */
    ::-moz-selection

    ::selection

## Examples

### HTML

    This text has special styles when you highlight it.
    <p>Also try selecting text in this paragraph.</p>

### CSS

    /* Make selected text gold on a red background */
    ::selection {
      color: gold;
      background-color: red;
    }

    /* Make selected text in a paragraph white on a blue background */
    p::selection {
      color: white;
      background-color: blue;
    }

### Result

## Accessibility concerns

**Don't override selected text styles for purely aesthetic reasons** — users can customize them to suit their needs. For people experiencing cognitive concerns or who are less technologically literate, unexpected changes to selection styles may hurt their understanding of the functionality.

If overridden, it is important to ensure that the **contrast ratio** between the text and background colors of the selection is high enough that people experiencing low vision conditions can read it.

Color contrast ratio is found by comparing the luminosity of the selected text and the selected text background colors. To meet current [Web Content Accessibility Guidelines (WCAG)](https://www.w3.org/WAI/intro/wcag), text content must have a contrast ratio of **4.5:1**, or 3:1 for larger text such as headings. (WCAG defines large text as between `18.66px` and `24px` and [bold](font-weight), or `24px` or larger.)

- [WebAIM: Color Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.3 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-pseudo-4/#selectordef-selection">CSS Pseudo-Elements Level 4<br />
<span class="small">The definition of '::selection' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

**Note:** `::selection` was in drafts of CSS Selectors Level 3, but it was removed in the Candidate Recommendation phase because its was under-specified (especially with nested elements) and interoperability wasn't achieved [(based on discussion in the W3C Style mailing list)](https://lists.w3.org/Archives/Public/www-style/2008Oct/0268.html). It returned in [Pseudo-Elements Level 4](https://dev.w3.org/csswg/css-pseudo-4/).

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

`::selection`

1

12

62

1

9

9.5

1.1

37

18

62

4

14

1

1.0

## See also

- [`pointer-events`](pointer-events) - control which events are active on the element

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/::selection" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/::selection</a>
