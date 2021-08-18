# -webkit-line-clamp

The `-webkit-line-clamp` CSS property allows limiting of the contents of a <span class="page-not-created">block container</span> to the specified number of lines.

It only works in combination with the [`display`](display) property set to `-webkit-box` or `-webkit-inline-box` and the [`-webkit-box-orient`](box-orient) property set to `vertical`.

In most cases you will also want to set [`overflow`](overflow) to `hidden`, otherwise the contents won't be clipped but an ellipsis will still be shown after the specified number of lines.

When applied to anchor elements, the truncating can happen in the middle of the text, not necessarily at the end.

**Note**: This property was originally implemented in WebKit and has some issues. It got standardized for legacy support. The [CSS Overflow Module Level 3](https://www.w3.org/TR/css-overflow-3/#propdef--webkit-line-clamp) specification also defines a <span class="page-not-created">`line-clamp`</span> property, which is meant to replace this property and avoid its issues.

## Syntax

    /* Keyword value */
    -webkit-line-clamp: none;

    /* <integer> values */
    -webkit-line-clamp: 3;
    -webkit-line-clamp: 10;

    /* Global values */
    -webkit-line-clamp: inherit;
    -webkit-line-clamp: initial;
    -webkit-line-clamp: unset;

`none`  
This value specifies that the content won't be clamped.

[`<integer>`](integer)  
This value specifies the number of lines after which the content will be clamped. It must be greater than 0.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>by computed value type</td></tr></tbody></table>

## Formal syntax

    none | <integer>

## Examples

### Truncating a paragraph

#### HTML

    <p>
      In this example the <code>-webkit-line-clamp</code> property is set to <code>3</code>, which means the text is clamped after three lines.
      An ellipsis will be shown at the point where the text is clamped.
    </p>

#### CSS

    p {
      width: 300px;
      display: -webkit-box;
      -webkit-box-orient: vertical;
      -webkit-line-clamp: 3;
      overflow: hidden;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-overflow-3/#propdef--webkit-line-clamp">CSS Overflow Module Level 3<br />
<span class="small">The definition of '-webkit-line-clamp' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`-webkit-line-clamp`

6

17

68

No

15

5

≤37

18

68

14

4.2

1.0

## See also

- [Line Clampin’ (Truncating Multiple Line Text)](https://css-tricks.com/line-clampin/)
- <span class="page-not-created">`line-clamp`</span>

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-line-clamp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-line-clamp</a>
