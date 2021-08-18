# overflow-clip-margin

The `overflow-clip-margin` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property determines how far outside its bounds an element with `overflow: clip` may be painted before being clipped.

## Syntax

    overflow-clip-margin: 20px;
    overflow-clip-margin: 1em;

    /* Global values */
    overflow-clip-margin: inherit;
    overflow-clip-margin: initial;
    overflow-clip-margin: unset;

The `overflow-block` property is specified as a length, negative values are not allowed.

If the element does not have `overflow: clip` then this property will be ignored.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0px</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>the computed</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <visual-box> || [0,∞]>where
    <visual-box> = content-box | padding-box | border-box

## Examples

### HTML

    <div class="box">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
    </div>

### CSS

    .box {
      border: 3px solid black;
      width:  250px;
      height: 100px;
      overflow: clip;
      overflow-clip-margin: 20px;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-overflow-3/#overflow-clip-margin">CSS Overflow Module Level 3<br />
<span class="small">The definition of 'overflow-clip-margin' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`overflow-clip-margin`

90

90

No

See [bug 1661582](https://bugzil.la/1661582).

No

No

No

90

90

No

No

No

No

## See also

- Related CSS properties: [`text-overflow`](text-overflow), [`white-space`](white-space), [`overflow`](overflow), [`overflow-inline`](overflow-inline), [`overflow-x`](overflow-x), [`overflow-y`](overflow-y), [`clip`](clip), [`display`](display)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-clip-margin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-clip-margin</a>
