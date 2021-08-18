# list-style

The `list-style` CSS [shorthand property](shorthand_properties) allows you to set all the list style properties at once.

**Note:** This property is applied to list items, i.e., elements with `display`: list-item; . [By default](https://www.w3.org/TR/html5/rendering.html#lists) this includes [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li) elements. Because this property is inherited, it can be set on a parent element (normally [`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol) or [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul)) to make the same list styling apply to all the items inside.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`list-style-image`](list-style-image)
- [`list-style-position`](list-style-position)
- [`list-style-type`](list-style-type)

## Syntax

    /* type */
    list-style: square;

    /* image */
    list-style: url('../img/shape.png');

    /* position */
    list-style: inside;

    /* type | position */
    list-style: georgian inside;

    /* type | image | position */
    list-style: lower-roman url('../img/shape.png') outside;

    /* Keyword value */
    list-style: none;

    /* Global values */
    list-style: inherit;
    list-style: initial;
    list-style: unset;

The `list-style` property is specified as one, two, or three keywords in any order. If [`list-style-type`](list-style-type) and [`list-style-image`](list-style-image) are both set, then `list-style-type` is used as a fallback if the image is unavailable.

### Values

[`list-style-type`](list-style-type)  
See [`list-style-type`](list-style-type).

[`list-style-image`](list-style-image)  
See [`list-style-image`](list-style-image).

[`list-style-position`](list-style-position)  
See [`list-style-position`](list-style-position).

`none`  
No list style is used.

## Accessibility concerns

Safari has an issue whereby unordered lists with a `list-style` value of `none` applied to them will not be recognized as a list in the accessibility tree. To address this, add a [zero-width space](https://en.wikipedia.org/wiki/Zero-width_space) as [pseudo-content](content) before each list item to ensure the list is recognized properly. This ensures the design is unaffected by the bug fix and that list items are not improperly described.

    ul {
      list-style: none;
    }

    ul li::before {
      content: "\200B";
    }

- [VoiceOver and list-style-type: none – Unfettered Thoughts](https://unfetteredthoughts.net/2017/09/26/voiceover-and-list-style-type-none/)
- [MDN Understanding WCAG, Guideline 1.3 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.3_%e2%80%94_create_content_that_can_be_presented_in_different_ways)
- [Understanding Success Criterion 1.3.1 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-programmatic.html)

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="list-style-type"><code>list-style-type</code></a>: <code>disc</code></li><li><a href="list-style-position"><code>list-style-position</code></a>: <code>outside</code></li><li><a href="list-style-image"><code>list-style-image</code></a>: <code>none</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>list items</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="list-style-image"><code>list-style-image</code></a>:</li><li><a href="list-style-position"><code>list-style-position</code></a>: as specified</li><li><a href="list-style-type"><code>list-style-type</code></a>: as specified</li></ul></td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <'list-style-type'> || <'list-style-position'> || <'list-style-image'>

## Examples

### Setting list style type and position

#### HTML

    List 1
    <ul class="one">
      <li>List Item1</li>
      <li>List Item2</li>
      <li>List Item3</li>
    </ul>
    List 2
    <ul class="two">
      <li>List Item A</li>
      <li>List Item B</li>
      <li>List Item C</li>
    </ul>

#### CSS

    .one {
      list-style: circle;
    }

    .two {
      list-style: square inside;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-lists-3/#list-style-property">CSS Lists Module Level 3<br />
<span class="small">The definition of 'list-style' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/generate.html#propdef-list-style">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'list-style' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`list-style`

1

12

1

4

7

1

1

18

4

10.1

1

1.0

`symbols`

No

No

35

No

No

No

No

No

35

No

No

No

## See also

- [`list-style-type`](list-style-type), [`list-style-image`](list-style-image), [`list-style-position`](list-style-position)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/list-style" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/list-style</a>
