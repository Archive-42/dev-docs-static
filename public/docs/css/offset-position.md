# offset-position

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `offset-position` CSS property defines the [initial position](https://www.w3.org/TR/motion-1/#valdef-offsetpath-initial-position) of the [`offset-path`](offset-path).

## Syntax

    /* Keyword values */
    offset-position: auto;
    offset-position: top;
    offset-position: bottom;
    offset-position: left;
    offset-position: right;
    offset-position: center;

    /* <percentage> values */
    offset-position: 25% 75%;

    /* <length> values */
    offset-position: 0 0;
    offset-position: 1cm 2cm;
    offset-position: 10ch 8em;

    /* Edge offsets values */
    offset-position: bottom 10px right 20px;
    offset-position: right 3em bottom 10px;
    offset-position: bottom 10px right;
    offset-position: top right 10px;

    /* Global values */
    offset-position: inherit;
    offset-position: initial;
    offset-position: unset;

### Values

`auto`  
The initial position is the position of the box specified by the [`position`](position) property.

`<position>`  
A [`<position>`](position_value). A position defines an x/y coordinate, to place an item relative to the edges of an element's box. It can be defined using one to four values. If two non-keyword values are used, the first value represents the horizontal position and the second represents the vertical position. If only one value is specified, the second value is assumed to be `center`. If three or four values are used, the length-percentage values are offsets for the preceding keyword value(s). For more explanation of these value types, see [`background-position`](background-position).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>transformable elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>referToSizeOfContainingBlock</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>for <a href="length"><code>&lt;length&gt;</code></a> the absolute value, otherwise a percentage</td></tr><tr class="even"><td>Animation type</td><td>a <a href="position_value#interpolation">position</a></td></tr></tbody></table>

## Formal syntax

    auto | <position>where
    <position> = [ [ left | center | right ] || [ top | center | bottom ] | [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ]? | [ [ left | right ] <length-percentage> ] && [ [ top | bottom ] <length-percentage> ] ]where
    <length-percentage> = <length> | <percentage>

## Examples

### Setting initial offset position

    <div id="motion-demo"></div>

    #motion-demo {
      offset-path: path('M20,20 C20,100 200,0 200,100');
      offset-position: left top;
      animation: move 3000ms infinite alternate ease-in-out;
      width: 40px;
      height: 40px;
      background: cyan;
    }

    @keyframes move {
      0% {
        offset-distance: 0%;
      }
      100% {
        offset-distance: 100%;
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/motion-1/#offset-position-property">Motion Path Module Level 1<br />
<span class="small">The definition of 'offset-position' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`offset-position`

No

See [bug 638055](https://crbug.com/638055)

No

No

See [bug 1559232](https://bugzil.la/1559232)

No

No

No

No

No

No

No

No

No

## See also

- [`offset`](offset)
- [`offset-anchor`](offset-anchor)
- [`offset-distance`](offset-distance)
- [`offset-path`](offset-path)
- [`offset-rotate`](offset-rotate)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/offset-position" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/offset-position</a>
