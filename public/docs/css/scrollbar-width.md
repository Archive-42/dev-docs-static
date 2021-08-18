# scrollbar-width

The `scrollbar-width` property allows the author to set the maximum thickness of an element’s scrollbars when they are shown.

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>scrolling boxes</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Syntax

    /* Keyword values */
    scrollbar-width: auto;
    scrollbar-width: thin;
    scrollbar-width: none;

    /* Global values */
    scrollbar-width: inherit;
    scrollbar-width: initial;
    scrollbar-width: unset;

### Values

&lt;scrollbar-width&gt;  
Defines the width of the scrollbar as a keyword. It must be one of the following values:

<table><tbody><tr class="odd"><td><code>auto</code></td><td>The default scrollbar width for the platform.</td></tr><tr class="even"><td><code>thin</code></td><td>A thin scrollbar width variant on platforms that provide that option, or a thinner scrollbar than the default platform scrollbar width.</td></tr><tr class="odd"><td><code>none</code></td><td>No scrollbar shown, however the element will still be scrollable.</td></tr></tbody></table>

**Note**: User Agents must apply any `scrollbar-width` value set on the root element to the viewport.

## Accessibility concerns

Use this property with caution — setting `scrollbar-width` to `thin` or `none` can make content hard or impossible to scroll if the author does not provide an alternative scrolling mechanism. While swiping gestures or mouse wheels can enable scrolling on such content, some devices have no scroll alternative.

WCAG criterion 2.1.1 (Keyboard) has been in place for a long time to advise on basic keyboard accessibility, and this should include scrolling of content areas. And introduced in WCAG 2.1, criterion 2.5.5 (Target Size) advises that touch targets should be at least 44px in width and height (although the problem is compounded on high-resolution screens; thorough testing is advised).

- [MDN Understanding WCAG, Guideline 2.1 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Operable#guideline_2.1_%e2%80%94_keyboard_accessible_make_all_functionality_available_from_a_keyboard)
- [MDN Understanding WCAG, Guideline 2.5 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Operable#guideline_2.5_input_modalities_make_it_easier_for_users_to_operate_functionality_through_various_inputs_beyond_keyboard.s/)
- [Understanding Success Criterion 2.1.1 | W3C Understanding WCAG 2.1](https://www.w3.org/WAI/WCAG21/Understanding/keyboard)
- [Understanding Success Criterion 2.5.5 | W3C Understanding WCAG 2.1](https://www.w3.org/WAI/WCAG21/Understanding/target-size.html)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>scrolling boxes</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | thin | none

## Examples

### Sizing overflow scrollbars

#### CSS

    .scroller {
      width: 300px;
      height: 100px;
      overflow-y: scroll;
      scrollbar-width: thin;
    }

#### HTML

    <div class="scroller">Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi welsh onion daikon amaranth tatsoi tomatillo melon azuki bean garlic. Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette tatsoi pea sprouts fava bean collard greens dandelion okra wakame tomato. Dandelion cucumber earthnut pea peanut soko zucchini.</div>

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-scrollbars-1/#scrollbar-width">CSS Scrollbars Level 1<br />
<span class="small">The definition of 'scrollbar-width' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial Definition</td></tr></tbody></table>

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

`scrollbar-width`

No

No

64

No

No

No

No

No

64

No

No

No

## See also

- <span class="page-not-created">`-ms-overflow-style`</span>
- [`::-webkit-scrollbar`](::-webkit-scrollbar)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scrollbar-width" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/scrollbar-width</a>
