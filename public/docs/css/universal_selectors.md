# Universal selectors

The CSS **universal selector** (`*`) matches elements of any type.

    /* Selects all elements */
    * {
      color: green;
    }

Universal selectors can be namespaced when using [`@namespace`](@namespace). This is useful when dealing with documents containing multiple namespaces such as HTML5 with inline SVG or MathML, or XML that mixes multiple vocabularies.

- `ns|*` - matches all elements in namespace _ns_
- `*|*` - matches all elements
- `|*` - matches all elements without any declared namespace

## Syntax

    * { style properties }

The asterisk is optional with simple selectors. For instance, `*.warning` and `.warning` are equivalent.

## Examples

### CSS

    * [lang^=en] {
      color: green;
    }

    *.warning {
      color: red;
    }

    *#maincontent {
      border: 1px solid blue;
    }

    .floating {
      float: left
    }

    /* automatically clear the next sibling after a floating element */
    .floating + * {
      clear: left;
    }

### HTML

    <p class="warning">
      <span lang="en-us">A green span</span> in a red paragraph.
    </p>
    <p id="maincontent" lang="en-gb">
      <span class="warning">A red span</span> in a green paragraph.
    </p>

### Result

### Namespaces

In this example the selector will only match elements in the example namespace.

    @namespace example url(http://www.example.com);
    example|* { color: blue }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#the-universal-selector">Selectors Level 4<br />
<span class="small">The definition of 'universal selector' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No changes</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#universal-selector">Selectors Level 3<br />
<span class="small">The definition of 'universal selector' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Defines behavior regarding namespaces and adds hint that omitting the selector is allowed within pseudo-elements</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/selector.html#universal-selector">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'universal selector' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`Universal_selectors`

1

12

1

7

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

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Universal_selectors" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/Universal_selectors</a>
