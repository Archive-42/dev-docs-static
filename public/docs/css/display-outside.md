# &lt;display-outside&gt;

The `<display-outside>` keywords specify the element’s outer [`display`](display) type, which is essentially its role in flow layout. These keywords are used as values of the `display` property, and can be used for legacy purposes as a single keyword, or as defined in the Level 3 specification alongside a value from the [`<display-inside>`](display-inside) keywords.

## Syntax

Valid `<display-outside>` values:

`block`  
The element generates a block element box, generating line breaks both before and after the element when in the normal flow.

`inline`  
The element generates one or more inline element boxes that do not generate line breaks before or after themselves. In normal flow, the next element will be on the same line if there is space

**Note**: Browsers that support the two value syntax, on finding the outer value only, such as when `display: block` or `display: inline` is specified, will set the inner value to `flow`. This will result in expected behavior; for example if you specify an element to be block, you would expect that the children of that element would participate in block and inline normal flow layout.

## Examples

In the following example, span elements (normally displayed as inline elements) are set to `display: block` and so break onto new lines and expand to fill their container in the inline dimension.

### HTML

    <span>span 1</span>
    <span>span 2</span>

### CSS

    span {
        display: block;
        border: 1px solid rebeccapurple;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-display/#typedef-display-outside">CSS Display Module Level 3<br />
<span class="small">The definition of 'display-outside' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td></tr></tbody></table>

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

`display-outside`

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

## See also

- [`display`](display)
  - [`<display-inside>`](display-inside)
  - [`<display-listitem>`](display-listitem)
  - [`<display-internal>`](display-internal)
  - [`<display-box>`](display-box)
  - [`<display-legacy>`](display-legacy)
- [Block and Inline layout in Normal Flow](css_flow_layout/block_and_inline_layout_in_normal_flow)
- [Formatting Contexts explained](css_flow_layout/intro_to_formatting_contexts)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/display-outside" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/display-outside</a>
