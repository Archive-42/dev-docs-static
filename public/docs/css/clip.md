# clip

The `clip` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines a visible portion of an element. The `clip` property applies only to absolutely positioned elements — that is, elements with [`position:absolute`](position) or [`position:fixed`](position).

    /* Keyword value */
    clip: auto;

    /* <shape> values */
    clip: rect(1px, 10em, 3rem, 2ch);

    /* Global values */
    clip: inherit;
    clip: initial;
    clip: unset;

## Syntax

**Note:** Where possible, authors are encouraged to use the newer [`clip-path`](clip-path) property instead.

### Values

[`<<shape>()>`](shape)  
A rectangular [`<<shape>()>`](shape) of the form `rect(<top>, <right>, <bottom>, <left>)`. The `<top>` and `<bottom>` values are offsets from the _inside top border edge_ of the box, while `<right>` and `<left>` are offsets from the _inside left border edge_ of the box — that is, the extent of the padding box.

The `<top>`, `<right>`, `<bottom>`, and `<left>` values may be either a [`<length>`](length) or `auto`. If any side's value is `auto`, the element is clipped to that side's _inside border edge_.

`auto`  
The element does not clip (default). This is different from `rect(auto, auto, auto, auto)`, which clips to the element’s inside border edges.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>absolutely positioned elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td><code>auto</code> if specified as <code>auto</code>, otherwise a rectangle with four values, each of which is <code>auto</code> if specified as <code>auto</code> or the computed length otherwise</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="shape#interpolation">rectangle</a></td></tr></tbody></table>

## Formal syntax

    <shape> | autowhere
    <shape> = rect(<top>, <right>, <bottom>, <left>)

## Examples

### Clipping an image

#### CSS

    .dotted-border {
      border: dotted;
      position: relative;
      width: 536px;
      height: 350px;
    }

    #top-left,
    #middle,
    #bottom-right {
      position: absolute;
      top: 0;
    }

    #top-left {
      left: 360px;
      clip: rect(0, 175px, 113px, 0);
    }

    #middle {
      left: 280px;
      clip: rect(119px, 255px, 229px, 80px);
    }

    #bottom-right {
      left: 200px;
      clip: rect(235px, 335px, 345px, 160px);
    }

#### HTML

    <p class="dotted-border">
      <img src="https://developer.mozilla.org/@api/deki/files/3613/=hut.jpg" title="Original graphic">
      <img id="top-left" src="https://developer.mozilla.org/@api/deki/files/3613/=hut.jpg" title="Graphic clipped to upper left">
      <img id="middle" src="https://developer.mozilla.org/@api/deki/files/3613/=hut.jpg" title="Graphic clipped towards middle">
      <img id="bottom-right" src="https://developer.mozilla.org/@api/deki/files/3613/=hut.jpg" title="Graphic clipped to bottom right">
    </p>

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/css-masking-1/#clip-property">CSS Masking Module Level 1<br />
<span class="small">The definition of 'clip' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Deprecates <code>clip</code> property, suggests <a href="clip-path"><code>clip-path</code></a> as replacement.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/visufx.html#clipping">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'clip' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`clip`

1

12

1

4

Before Internet Explorer 7, Internet Explorer incorrectly interprets `clip: auto` as `clip: rect(auto, auto, auto, auto)`.

7

1

Safari incorrectly interprets `clip: auto` as `clip: rect(auto, auto, auto, auto)`.

37

18

4

14

1

Safari incorrectly interprets `clip: auto` as `clip: rect(auto, auto, auto, auto)`.

1.0

## See also

- This property is deprecated. Use [`clip-path`](clip-path) instead.
- Related CSS properties: [`text-overflow`](text-overflow), [`white-space`](white-space), [`overflow-x`](overflow-x), [`overflow-y`](overflow-y), [`overflow`](overflow), [`display`](display), [`position`](position)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/clip" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/clip</a>
