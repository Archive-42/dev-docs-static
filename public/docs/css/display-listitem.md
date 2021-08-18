# &lt;display-listitem&gt;

The `list-item` keyword causes the element to generate a `::marker` pseudo-element with the content specified by its [`list-style`](list-style) properties (for example a bullet point) together with a principal box of the specified type for its own contents.

## Syntax

A single value of `list-item` will cause the element to behave like a list item. This can be used together with [`list-style-type`](list-style-type) and [`list-style-position`](list-style-position).

`list-item` can also be combined with any [`<display-outside>`](display-outside) keyword and the `flow` or `flow-root` [`<display-inside>`](display-inside) keywords.

**Note**: In browsers that support the two-value syntax, if no inner value is specified it will default to `flow`. If no outer value is specified, the principal box will have an outer display type of `block`.

## Examples

### HTML

    <div class="fake-list">I will display as a list item</div>

### CSS

    .fake-list {
      display: list-item;
      list-style-position: inside;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-display/#typedef-display-listitem">CSS Display Module Level 3<br />
<span class="small">The definition of 'display-listitem' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td></tr></tbody></table>

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

`display-listitem`

1

12

1

6

7

1

≤37

18

4

14

1

1.0

`legend-support`

71

79

64

No

58

No

71

71

64

50

No

10.0

BCD tables only load in the browser

## See also

- [`display`](display)
  - [`<display-outside>`](display-outside)
  - [`<display-inside>`](display-inside)
  - [`<display-internal>`](display-internal)
  - [`<display-box>`](display-box)
  - [`<display-legacy>`](display-legacy)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/display-listitem" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/display-listitem</a>
