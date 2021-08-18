# :link

The `:link` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents an element that has not yet been visited. It matches every unvisited [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) or [`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area) element that has an `href` attribute.

    /* Selects any <a> that has not been visited yet */
    a:link {
      color: red;
    }

Styles defined by the `:link` pseudo-class will be overridden by any subsequent link-related pseudo-class ([`:active`](:active), [`:hover`](:hover), or [`:visited`](:visited)) that has at least equal specificity. To style links appropriately, put the `:link` rule before all other link-related rules, as defined by the _LVHA-order_: `:link` — `:visited` — `:hover` — `:active`.

**Note:** Use [`:any-link`](:any-link) to select an element independent of whether it has been visited or not.

## Syntax

    :link

## Examples

By default, most browsers apply a special [`color`](color) value to visited links. Thus, the links in this example will probably have special font colors only before you visit them. (After that, you'll need to clear your browser history to see them again.) However, the [`background-color`](background-color) values are likely to remain, as most browsers do not set that property on visited links by default.

### HTML

    <a href="#ordinary-target">This is an ordinary link.</a><br>
    <a href="">You've already visited this link.</a><br>
    <a>Placeholder link (won't get styled)</a>

### CSS

    a:link {
      background-color: gold;
      color: green;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#selector-link">HTML Living Standard<br />
<span class="small">The definition of ':link' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-4/#link">Selectors Level 4<br />
<span class="small">The definition of ':link' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-3/#link">Selectors Level 3<br />
<span class="small">The definition of ':link' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/selector.html#link-pseudo-classes">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of ':link' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Lift the restriction to only apply it for <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a"><code>&lt;a&gt;</code></a> element.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#anchor-pseudo-classes">CSS Level 1<br />
<span class="small">The definition of ':link' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:link`

1

12

1

3

3.5

1

1.5

18

4

14

3.2

1.0

`not_match_link`

1

12

87

No

3.5

No

Safari currently matches `<link>` elements with link pseudo-classes. See [Bug: 220740](https://webkit.org/b/220740).

1.5

18

87

14

No

Safari currently matches `<link>` elements with link pseudo-classes. See [Bug: 220740](https://webkit.org/b/220740).

1.0

## See also

- Link-related pseudo-classes: [`:visited`](:visited), [`:hover`](:hover), [`:active`](:active)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:link" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:link</a>
