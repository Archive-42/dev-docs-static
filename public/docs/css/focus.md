# :focus

The `:focus` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents an element (such as a form input) that has received focus. It is generally triggered when the user clicks or taps on an element or selects it with the keyboard's Tab key.

    /* Selects any <input> when focused */
    input:focus {
      color: red;
    }

**Note:** This pseudo-class applies only to the focused element itself. Use [`:focus-within`](:focus-within) if you want to select an element that _contains_ a focused element.

## Syntax

    :focus

## Examples

### HTML

    <input class="red-input" value="I'll be red when focused."><br>
    <input class="blue-input" value="I'll be blue when focused.">

### CSS

    .red-input:focus {
      background: yellow;
      color: red;
    }

    .blue-input:focus {
      background: yellow;
      color: blue;
    }

### Result

## Accessibility concerns

Make sure the visual focus indicator can be seen by people with low vision. This will also benefit anyone use a screen in a brightly lit space (like outside in the sun). [WCAG 2.1 SC 1.4.11 Non-Text Contrast](https://www.w3.org/WAI/WCAG21/Understanding/non-text-contrast.html) requires that the visual focus indicator be at least 3 to 1.

- Accessible Visual Focus Indicators: [Give Your Site Some Focus! Tips for Designing Useful and Usable Focus Indicators](https://www.deque.com/blog/give-site-focus-tips-designing-usable-focus-indicators/)

### `:focus { outline: none; }`

Never just remove the focus outline (visible focus indicator) without replacing it with a focus outline that will pass [WCAG 2.1 SC 1.4.11 Non-Text Contrast](https://www.w3.org/WAI/WCAG21/Understanding/non-text-contrast.html).

- Quick Tip: [Never remove CSS outlines](https://a11yproject.com/posts/never-remove-css-outlines/)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#selector-focus">HTML Living Standard<br />
<span class="small">The definition of ':focus' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Defines HTML-specific semantics.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-4/#focus-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':focus' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-3/#the-user-action-pseudo-classes-hover-act">Selectors Level 3<br />
<span class="small">The definition of ':focus' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/selector.html#dynamic-pseudo-classes">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of ':focus' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:focus`

1

12

1

8

7

1

1

18

4

10.1

1

1.0

## See also

- [`:focus-visible`](:focus-visible) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`:focus-within`](:focus-within)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:focus" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:focus</a>
