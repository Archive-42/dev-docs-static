# overflow-anchor

The `overflow-anchor` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property provides a way to opt out of the browser's scroll anchoring behavior, which adjusts scroll position to minimize content shifts.

Scroll anchoring behavior is enabled by default in any browser that supports it. Therefore, changing the value of this property is typically only required if you are experiencing problems with scroll anchoring in a document or part of a document and need to turn the behavior off.

## Syntax

    /* Keyword values */
    overflow-anchor: auto;
    overflow-anchor: none;

    /* Global values */
    overflow-anchor: inherit;
    overflow-anchor: initial;
    overflow-anchor: unset;

### Values

`auto`  
The element becomes a potential anchor when adjusting scroll position.

`none`  
The element won't be selected as a potential anchor.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | none

## Examples

### Prevent scroll anchoring

To prevent scroll anchoring in a document, use the `overflow-anchor` property.

    * {
      overflow-anchor: none;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-scroll-anchoring/#propdef-overflow-anchor">CSS Scroll Anchoring Module Level 1<br />
<span class="small">The definition of 'overflow-anchor' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`overflow-anchor`

56

79

66

No

43

No

56

56

No

43

No

6.0

## See also

- [Guide to scroll anchoring](overflow-anchor/guide_to_scroll_anchoring)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-anchor</a>
