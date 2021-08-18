# offset-rotate

The `offset-rotate` CSS property defines the orientation/direction of the element as it is positioned along the [`offset-path`](offset-path).

**Note**: Early versions of the spec called this property `motion-rotation`.

## Syntax

    /* Follow the path direction, with optional additional angle */
    offset-rotate: auto;
    offset-rotate: auto 45deg;

    /* Follow the path direction but facing the opposite direction of `auto` */
    offset-rotate: reverse;

    /* Keep a constant rotation regardless the position on the path */
    offset-rotate: 90deg;
    offset-rotate: .5turn;

`auto`  
The element is rotated by the angle of the direction of the [`offset-path`](offset-path), relative to the positive x-axis. This is the default value.

`<angle>`  
The element has a constant clockwise rotation transformation applied to it by the specified rotation angle.

`auto <angle>`  
If `auto` is followed by an [`<angle>`](angle), the computed value of <span id="ref-for-angle-value①③" class="production">the angle</span> is added to the computed value of `auto`.

`reverse`  
The element is rotated similar to `auto`, except it faces the opposite direction. It is the same as specifying a value of `auto 180deg`.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>transformable elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>as &lt;angle&gt;, &lt;basic-shape&gt; or &lt;path()&gt;</td></tr></tbody></table>

## Formal syntax

    [ auto | reverse ] || <angle>

## Examples

### Setting element orientation along its offset path

#### HTML

    <div></div>
    <div></div>
    <div></div>

#### CSS

    div {
      width: 40px;
      height: 40px;
      background: #2BC4A2;
      margin: 20px;
      clip-path: polygon(0% 0%, 70% 0%, 100% 50%, 70% 100%, 0% 100%, 30% 50%);
      animation: move 5000ms infinite alternate ease-in-out;

      offset-path: path('M20,20 C20,50 180,-10 180,20');
    }
    div:nth-child(1) {
      offset-rotate: auto;
    }
    div:nth-child(2) {
      offset-rotate: auto 90deg;
    }
    div:nth-child(3) {
      offset-rotate: 30deg;
    }

    @keyframes move {
      100% {
        offset-distance: 100%;
      }
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/motion-1/#offset-rotate-property">Motion Path Module Level 1<br />
<span class="small">The definition of 'offset-rotate' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`offset-rotate`

56

55

46

79

79

79

72

69-72

No

43

42

33

No

56

55

46

56

55

46

No

43

42

33

No

6.0

6.0

5.0

## See also

- [`offset`](offset)
- [`offset-anchor`](offset-anchor)
- [`offset-distance`](offset-distance)
- [`offset-path`](offset-path)
- [`offset-position`](offset-position)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/offset-rotate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/offset-rotate</a>
