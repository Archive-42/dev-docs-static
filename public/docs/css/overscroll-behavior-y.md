# overscroll-behavior-y

The `overscroll-behavior-y` CSS property sets the browser's behavior when the vertical boundary of a scrolling area is reached.

See [`overscroll-behavior`](overscroll-behavior) for a full explanation.

    /* Keyword values */
    overscroll-behavior-y: auto; /* default */
    overscroll-behavior-y: contain;
    overscroll-behavior-y: none;

    /* Global values */
    overscroll-behavior-y: inherit;
    overscroll-behavior-y: initial;
    overscroll-behavior-y: unset;

## Syntax

The `overscroll-behavior-y` property is specified as a keyword chosen from the list of values below.

### Values

`auto`  
The default scroll overflow behavior occurs as normal.

`contain`  
Default scroll overflow behavior is observed inside the element this value is set on (e.g. "bounce" effects or refreshes), but no scroll chaining occurs to neighboring scrolling areas, e.g. underlying elements will not scroll.

`none`  
No scroll chaining occurs to neighboring scrolling areas, and default scroll overflow behavior is prevented.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>non-replaced block-level elements and non-replaced inline-block elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    contain | none | auto

## Examples

### Preventing an underlying element from scrolling vertically

    .messages {
      height: 220px;
      overflow: auto;
      overscroll-behavior-y: contain;
    }

See [`overscroll-behavior`](overscroll-behavior) for a full example and explanation.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-overscroll-1/#propdef-overscroll-behavior-y">CSS Overscroll Behavior Module Level 1<br />
<span class="small">The definition of 'overscroll-behavior-y' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`overscroll-behavior-y`

63

18

Currently the `none` value incorrectly behaves as `contain` (allowing for the elastic bounce effect).

59

No

50

No

See [bug 176454](https://webkit.org/b/176454).

63

63

59

46

No

See [bug 176454](https://webkit.org/b/176454).

8.0

## See also

- [Take control of your scroll: customizing pull-to-refresh and overflow effects](https://developers.google.com/web/updates/2017/11/overscroll-behavior#demo)
- The mapped logical properties: [`overscroll-behavior-inline`](overscroll-behavior-inline), [`overscroll-behavior-block`](overscroll-behavior-block)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-y" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-y</a>
