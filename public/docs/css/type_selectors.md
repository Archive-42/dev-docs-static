# Type selectors

The CSS **type selector** matches elements by node name. In other words, it selects all elements of the given type within a document.

    /* All <a> elements. */
    a {
      color: red;
    }

Type selectors can be namespaced when using [`@namespace`](@namespace). This is useful when dealing with documents containing multiple namespaces such as HTML5 with inline SVG or MathML, or XML that mixes multiple vocabularies.

- `ns|h1` - matches `<h1>` elements in namespace _ns_
- `*|h1` - matches all `<h1>` elements
- `|h1` - matches all `<h1>` elements without any declared namespace

## Syntax

    element { style properties }

## Examples

### CSS

    span {
      background-color: skyblue;
    }

### HTML

    <span>Here's a span with some text.</span>
    <p>Here's a p with some text.</p>
    <span>Here's a span with more text.</span>

### Result

### Namespaces

In this example the selector will only match `<h1>` elements in the example namespace.

    @namespace example url(http://www.example.com);
    example|h1 { color: blue }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#type-selectors">Selectors Level 4<br />
<span class="small">The definition of 'Type (tag name) selector' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No changes</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#type-selectors">Selectors Level 3<br />
<span class="small">The definition of 'type selectors' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No changes</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/selector.html#type-selectors">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'type selectors' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#basic-concepts">CSS Level 1<br />
<span class="small">The definition of 'type selectors' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`Type_selectors`

1

12

1

3

3.5

1

≤37

18

4

10.1

1

1.0

`namespaces`

1

12

1

9

8

1.3

≤37

18

4

10.1

1

1.0

## See also

- [CSS Selectors](css_selectors)
- [Learn CSS: Selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Type_selectors" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/Type_selectors</a>
