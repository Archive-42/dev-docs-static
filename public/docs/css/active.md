# :active

The `:active` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents an element (such as a button) that is being activated by the user. When using a mouse, "activation" typically starts when the user presses down the primary mouse button.

    /* Selects any <a> that is being activated */
    a:active {
      color: red;
    }

The `:active` pseudo-class is commonly used on [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) and [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) elements. Other common targets of this pseudo-class include elements that _contain_ an activated element, and form elements that are being activated through their associated [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label).

Styles defined by the `:active` pseudo-class will be overridden by any subsequent link-related pseudo-class ([`:link`](:link), [`:hover`](:hover), or [`:visited`](:visited)) that has at least equal specificity. To style links appropriately, put the `:active` rule after all other link-related rules, as defined by the _LVHA-order_: `:link` — `:visited` — `:hover` — `:active`.

**Note:** On systems with multi-button mice, CSS3 specifies that the `:active` pseudo-class must only apply to the primary button; on right-handed mice, this is typically the leftmost button.

## Syntax

    :active

## Examples

### Active links

#### HTML

    <p>This paragraph contains a link:
      <a href="#">This link will turn red while you click on it.</a>
      The paragraph will get a gray background while you click on it or the link.
    </p>

#### CSS

    a:link { color: blue; }          /* Unvisited links */
    a:visited { color: purple; }     /* Visited links */
    a:hover { background: yellow; }  /* Hovered links */
    a:active { color: red; }         /* Active links */

    p:active { background: #eee; }   /* Active paragraphs */

#### Result

### Active form elements

#### HTML

    <form>
      <label for="my-button">My button: </label>
      <button id="my-button" type="button">Try Clicking Me or My Label!</button>
    </form>

#### CSS

    form :active {
      color: red;
    }

    form button {
      background: white;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#selector-active">HTML Living Standard<br />
<span class="small">The definition of ':active' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-4/#active-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':active' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-3/#useraction-pseudos">Selectors Level 3<br />
<span class="small">The definition of ':active' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/selector.html#dynamic-pseudo-classes">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of ':active' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#anchor-pseudo-classes">CSS Level 1<br />
<span class="small">The definition of ':active' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:active`

1

12

1

4

5

1

1

18

4

10.1

1

1.0

`non_a_elements`

1

12

1

8

7

1

1

18

4

14

1

By default, Safari on iOS does not use the [`:active`](https://developer.mozilla.org/docs/Web/CSS/:active) state unless there is a [`touchstart`](https://developer.mozilla.org/docs/Web/Reference/Events/touchstart) event handler on the relevant element or on the [`<body>`](https://developer.mozilla.org/docs/Web/HTML/Element/body) element.

1.0

## See also

- Link-related pseudo-classes: [`:link`](:link), [`:visited`](:visited), and [`:hover`](:hover)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:active" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:active</a>
