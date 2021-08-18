# :visited

The `:visited` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents links that the user has already visited. For privacy reasons, the styles that can be modified using this selector are very limited.

    /* Selects any <a> that has been visited */
    a:visited {
      color: green;
    }

Styles defined by the `:visited` pseudo-class will be overridden by any subsequent link-related pseudo-class ([`:link`](:link), [`:hover`](:hover), or [`:active`](:active)) that has at least equal specificity. To style links appropriately, put the `:visited` rule after the `:link` rule but before the `:hover` and `:active` rules, as defined by the _LVHA-order_: `:link` — `:visited` — `:hover` — `:active`.

## Privacy restrictions

For privacy reasons, browsers strictly limit which styles you can apply using this pseudo-class, and how they can be used:

- Allowable CSS properties are [`color`](color), [`background-color`](background-color), [`border-color`](border-color), [`border-bottom-color`](border-bottom-color), [`border-left-color`](border-left-color), [`border-right-color`](border-right-color), [`border-top-color`](border-top-color), [`column-rule-color`](column-rule-color), [`outline-color`](outline-color), [`text-decoration-color`](text-decoration-color), and [`text-emphasis-color`](text-emphasis-color).
- Allowable SVG attributes are `fill` and `stroke`.
- The alpha component of the allowed styles will be ignored. The alpha component of the element's non-`:visited` state will be used instead, except when that component is `0`, in which case the style set in `:visited` will be ignored entirely.
- Although these styles can change the appearance of colors to the end user, the [`window.getComputedStyle`](https://developer.mozilla.org/en-US/docs/Web/API/Window/getComputedStyle) method will lie and always return the value of the non-`:visited` color.
- The `<link>` element is never matched by `:visited`.

**Note:** For more information on these limitations and the reasons behind them, see [Privacy and the :visited selector](Privacy_and_the_:visited_selector).

## Syntax

    :visited

## Examples

Properties that would otherwise have no color or be transparent cannot be modified with `:visited`. Of the properties that can be set with this pseudo-class, your browser probably has a default value for `color` and `column-rule-color` only. Thus, if you want to modify the other properties, you'll need to give them a base value outside the `:visited` selector.

### HTML

    <a href="#test-visited-link">Have you visited this link yet?</a><br>
    <a href="">You've already visited this link.</a>

### CSS

    a {
      /* Specify non-transparent defaults to certain properties,
         allowing them to be styled with the :visited state */
      background-color: white;
      border: 1px solid white;
    }

    a:visited {
      background-color: yellow;
      border-color: hotpink;
      color: hotpink;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#selector-visited">HTML Living Standard<br />
<span class="small">The definition of ':visited' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-4/#link">Selectors Level 4<br />
<span class="small">The definition of ':visited' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-3/#link">Selectors Level 3<br />
<span class="small">The definition of ':visited' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/selector.html#link-pseudo-classes">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of ':visited' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Lifts the restriction to only apply <code>:visited</code> to the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a"><code>&lt;a&gt;</code></a> element. Lets browsers restrict its behavior for privacy reasons.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#anchor-pseudo-classes">CSS Level 1<br />
<span class="small">The definition of ':visited' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:visited`

1

12

1

4

3.5

1

4.4

18

4

10.1

1

1.0

`not_match_link`

1

12

87

No

15

No

Safari currently matches `<link>` elements with link pseudo-classes. See [Bug: 220740](https://webkit.org/b/220740).

4.4

18

87

14

No

Safari currently matches `<link>` elements with link pseudo-classes. See [Bug: 220740](https://webkit.org/b/220740).

1.0

`privacy_measures`

6

12

4

8

15

5

37

18

4

14

4.2

1.0

## See also

- [Privacy and the :visited selector](Privacy_and_the_:visited_selector)
- Link-related pseudo-classes: [`:link`](:link), [`:active`](:active), [`:hover`](:hover)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:visited" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:visited</a>
