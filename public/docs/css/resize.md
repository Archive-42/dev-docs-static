# resize

The `resize` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets whether an element is resizable, and if so, in which directions.

`resize` does not apply to the following:

- Inline elements
- Block elements for which the [`overflow`](overflow) property is set to `visible`

## Syntax

    /* Keyword values */
    resize: none;
    resize: both;
    resize: horizontal;
    resize: vertical;
    resize: block;
    resize: inline;

    /* Global values */
    resize: inherit;
    resize: initial;
    resize: unset;

The `resize` property is specified as a single keyword value from the list below.

### Values

`none`  
The element offers no user-controllable method for resizing it.

`both`  
The element displays a mechanism for allowing the user to resize it, which may be resized both horizontally and vertically.

`horizontal`  
The element displays a mechanism for allowing the user to resize it in the _horizontal_ direction.

`vertical`  
The element displays a mechanism for allowing the user to resize it in the _vertical_ direction.

`block` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The element displays a mechanism for allowing the user to resize it in the _block_ direction (either horizontally or vertically, depending on the [`writing-mode`](writing-mode) and [`direction`](direction) value).

`inline` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The element displays a mechanism for allowing the user to resize it in the _inline_ direction (either horizontally or vertically, depending on the [`writing-mode`](writing-mode) and [`direction`](direction) value).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>elements with <a href="overflow"><code>overflow</code></a> other than <code>visible</code>, and optionally replaced elements representing images or videos, and iframes</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    none | both | horizontal | vertical | block | inline

## Examples

### Disabling resizability of textareas

In many browsers, [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) elements are resizable by default. You may override this behavior with the `resize` property.

#### HTML

    <textarea>Type some text here.</textarea>

#### CSS

    textarea {
      resize: none; /* Disables resizability */
    }

#### Result

### Using resize with arbitrary elements

You can use the `resize` property to make any element resizable. In the example below, a resizable [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) contains a resizable paragraph ([`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) element).

#### HTML

    <div class="resizable">
      <p class="resizable">
        This paragraph is resizable in all directions, because
        the CSS `resize` property is set to `both` on this element.
      </p>
    </div>

#### CSS

    .resizable {
      resize: both;
      overflow: scroll;
      border: 1px solid black;
    }

    div {
      height: 300px;
      width: 300px;
    }

    p {
      height: 200px;
      width: 200px;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-ui-3/#resize">CSS Basic User Interface Module Level 3<br />
<span class="small">The definition of 'resize' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`resize`

1

79

4

No

12.1

3

37

18

4

14

1

1.0

`block_level_support`

4

79

5

`resize` doesn't have any effect on [`<iframe>`](https://developer.mozilla.org/docs/Web/HTML/Element/iframe). See [bug 680823](https://bugzil.la/680823))

No

15

4

37

18

5

`resize` doesn't have any effect on [`<iframe>`](https://developer.mozilla.org/docs/Web/HTML/Element/iframe). See [bug 680823](https://bugzil.la/680823))

14

3.2

1.0

`flow_relative_support`

No

No

63

No

No

No

No

No

63

No

No

No

## See also

- [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/resize" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/resize</a>
