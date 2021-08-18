# list-style-position

The `list-style-position` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the position of the [`::marker`](::marker) relative to a list item.

It is often more convenient to use the shorthand [`list-style`](list-style).

**Note:** This property is applied to list items, i.e., elements with `display`: list-item;. [By default](https://www.w3.org/TR/html5/rendering.html#lists) this includes [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li) elements. Because this property is inherited, it can be set on the parent element (normally [`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol) or [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul)) to let it apply to all list items.

Note that there is variance among browsers regarding behavior when a block element is placed first within a list element declared as `list-style-position: inside`. Chrome and Safari both place this element on the same line as the marker box, whereas Firefox, Internet Explorer, and Opera place it on the next line. For more information on this, see [bug 36854](https://bugzilla.mozilla.org/show_bug.cgi?id=36854).

## Syntax

    /* Keyword values */
    list-style-position: inside;
    list-style-position: outside;

    /* Global values */
    list-style-position: inherit;
    list-style-position: initial;
    list-style-position: unset;

The `list-style-position` property is specified as one of the keyword values listed below.

### Values

`inside`  
The [`::marker`](::marker) is the first element among the list item's contents.

`outside`  
The [`::marker`](::marker) is outside the principal block box.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>outside</code></td></tr><tr class="even"><td>Applies to</td><td>list items</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    inside | outside

## Examples

### Setting list item position

#### HTML

    <ul class="inside">List 1
      <li>List Item 1-1</li>
      <li>List Item 1-2</li>
      <li>List Item 1-3</li>
      <li>List Item 1-4</li>
    </ul>
    <ul class="outside">List 2
      <li>List Item 2-1</li>
      <li>List Item 2-2</li>
      <li>List Item 2-3</li>
      <li>List Item 2-4</li>
    </ul>
    <ul class="inside-img">List 3
      <li>List Item 3-1</li>
      <li>List Item 3-2</li>
      <li>List Item 3-3</li>
      <li>List Item 3-4</li>
    </ul>

#### CSS

    .inside {
      list-style-position: inside;
      list-style-type: square;
    }

    .outside {
      list-style-position: outside;
      list-style-type: circle;
    }

    .inside-img {
      list-style-position: inside;
      list-style-image: url("https://mdn.mozillademos.org/files/11979/starsolid.gif");
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-lists-3/#list-style-position-property">CSS Lists Module Level 3<br />
<span class="small">The definition of 'list-style-position' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/generate.html#propdef-list-style-position">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'list-style-position' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`list-style-position`

1

12

1

4

3.5

1

≤37

18

4

14

1

1.0

## See also

- [`list-style`](list-style), [`list-style-type`](list-style-type), [`list-style-image`](list-style-image)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-position" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-position</a>
