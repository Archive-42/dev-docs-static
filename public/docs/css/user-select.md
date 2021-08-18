# user-select

The `user-select` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property controls whether the user can select text. This doesn't have any effect on content loaded as part of a browser's user interface (its [chrome](https://developer.mozilla.org/en-US/docs/Glossary/Chrome)), except in textboxes.

    /* Keyword values */
    user-select: none;
    user-select: auto;
    user-select: text;
    user-select: contain;
    user-select: all;

    /* Global values */
    user-select: inherit;
    user-select: initial;
    user-select: unset;

    /* Mozilla-specific values */
    -moz-user-select: none;
    -moz-user-select: text;
    -moz-user-select: all;

    /* WebKit-specific values */
    -webkit-user-select: none;
    -webkit-user-select: text;
    -webkit-user-select: all; /* Doesn't work in Safari; use only
                                 "none" or "text", or else it will
                                 allow typing in the <html> container */

    /* Microsoft-specific values */
    -ms-user-select: none;
    -ms-user-select: text;
    -ms-user-select: element;

**Note**: `user-select` is not an inherited property, though the initial `auto` value makes it behave like it is inherited most of the time. WebKit/Chromium-based browsers _do_ implement the property as inherited, which violates the behavior described in the spec, and this will bring some issues. Until now, Chromium chooses to [fix the issues](https://chromium.googlesource.com/chromium/src/+/b01af0b296ecb855aac95c4ed335d188e6eac2de), make the final behavior meets the specifications.

## Syntax

`none`  
The text of the element and its sub-elements is not selectable. Note that the [`Selection`](https://developer.mozilla.org/en-US/docs/Web/API/Selection) object can contain these elements.

`auto`  
The used value of `auto` is determined as follows:

- On the `::before` and `::after` pseudo elements, the used value is `none`
- If the element is an editable element, the used value is `contain`
- Otherwise, if the used value of `user-select` on the parent of this element is `all`, the used value is `all`
- Otherwise, if the used value of `user-select` on the parent of this element is `none`, the used value is `none`
- Otherwise, the used value is `text`

`text`  
The text can be selected by the user.

`all`  
The content of the element shall be selected atomically: If a selection would contain part of the element, then the selection must contain the entire element including all its descendants. If a double-click or context-click occurred in sub-elements, the highest ancestor with this value will be selected.

`contain`  
Enables selection to start within the element; however, the selection will be contained by the bounds of that element.

`element`<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> (IE-specific alias)  
Same as `contain`. Supported only in Internet Explorer.

**Note:** CSS UI 4 [renames `user-select: element` to `contain`](https://github.com/w3c/csswg-drafts/commit/3f1d9db96fad8d9fc787d3ed66e2d5ad8cfadd05).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | text | none | contain | all

## Examples

### HTML

    <p>You should be able to select this text.</p>
    <p class="unselectable">Hey, you can't select this text!</p>
    <p class="all">Clicking once will select all of this text.</p>

### CSS

    .unselectable {
      -moz-user-select: none;
      -webkit-user-select: none;
      -ms-user-select: none;
      user-select: none;
    }

    .all {
      -moz-user-select: all;
      -webkit-user-select: all;
      -ms-user-select: all;
      user-select: all;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-ui-4/#propdef-user-select">CSS Basic User Interface Module Level 4<br />
<span class="small">The definition of 'user-select' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition. Also defines <code>-webkit-user-select</code> as a deprecated alias of <code>user-select</code>.</td></tr></tbody></table>

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

`user-select`

54

1

12

12

69

49

1

44

10

15

3

2-3

54

≤37

54

18

49

4

44

14

3

6.0

1.0

`all`

53

79

1

No

40

No

53

53

4

41

No

6.0

`auto`

1

12

1

10

15

2

≤37

18

4

14

3

1.0

`contain`

No

12-79

No

10

No

No

No

No

No

No

No

No

`none`

1

12

21

1-65

10

15

2

≤37

18

21

4-65

14

3

1.0

`text`

1

12

1

10

15

2

Allows typing in the `<html>` container.

≤37

18

4

14

3

Allows typing in the `<html>` container.

1.0

## See also

- [`::selection`](::selection) pseudo-element
- The JavaScript [`Selection`](https://developer.mozilla.org/en-US/docs/Web/API/Selection) object

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/user-select" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/user-select</a>
