# :root

The `:root` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) matches the root element of a tree representing the document. In HTML, `:root` represents the [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html) element and is identical to the selector `html`, except that its [specificity](specificity) is higher.

    /* Selects the root element of the document:
       <html> in the case of HTML */
    :root {
      background: yellow;
    }

## Syntax

    :root

## Examples

### Declaring global CSS variables

`:root` can be useful for declaring global [CSS variables](using_css_custom_properties):

    :root {
      --main-color: hotpink;
      --pane-padding: 5px 42px;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#root-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':root' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#root-pseudo">Selectors Level 3<br />
<span class="small">The definition of ':root' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:root`

1

12

1

9

9.5

1

37

18

4

14

1

1.0

## See also

- [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html)
- [`Document.rootElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/rootElement)
- [`Node.getRootNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/getRootNode)
- [`Element.shadowRoot`](https://developer.mozilla.org/en-US/docs/Web/API/Element/shadowRoot)
- [`ShadowRoot`](https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:root" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:root</a>
