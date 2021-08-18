# zoom

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The non-standard **`zoom`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property can be used to control the magnification level of an element. [`transform: scale()`](<transform-function/scale()>) should be used instead of this property, if possible. However, unlike CSS Transforms, `zoom` affects the layout size of the element.

    /* Keyword values */
    zoom: normal;
    zoom: reset;

    /* <percentage> values */
    zoom: 50%;
    zoom: 200%;

    /* <number> values */
    zoom: 1.1;
    zoom: 0.7;

    /* Global values */
    zoom: inherit;
    zoom: initial;
    zoom: unset;

## Syntax

### Values

`normal`  
Render this element at its normal size.

`reset` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Do not (de)magnify this element if the user applies non-pinch-based zooming (e.g. by pressing Ctrl-- or Ctrl++ keyboard shortcuts) to the document. Only supported by WebKit (and possibly Blink).

[`<percentage>`](percentage)  
Zoom factor. `100%` is equivalent to `normal`. Values larger than `100%` zoom in. Values smaller than `100%` zoom out.

[`<number>`](number)  
Zoom factor. Equivalent to the corresponding percentage (`1.0` = `100%` = `normal`). Values larger than `1.0` zoom in. Values smaller than `1.0` zoom out.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>an <a href="integer#interpolation">integer</a></td></tr></tbody></table>

## Formal syntax

    normal | reset | <number> | <percentage>

## Examples

### First example

#### HTML

    <p class="small">Small</p>
    <p class="normal">Normal</p>
    <p class="big">Big</p>

#### CSS

    p.small {
      zoom: 75%;
    }
    p.normal {
      zoom: normal;
    }
    p.big {
      zoom: 2.5;
    }
    p {
      display: inline-block;
    }
    p:hover {
      zoom: reset;
    }

#### Result

### Second example

#### HTML

    <div id="a" class="circle"></div>
    <div id="b" class="circle"></div>
    <div id="c" class="circle"></div>

#### CSS

    div.circle {
      width: 25px;
      height: 25px;
      border-radius: 100%;
      text-align: center;
      vertical-align: middle;
      display: inline-block;
      zoom: 1.5;
    }
    div#a {
      background-color: gold;
      zoom: normal;
    }
    div#b {
      background-color: green;
      zoom: 200%;
    }
    div#c {
      background-color: blue;
      zoom: 2.9;
    }

#### Result

## Specifications

Not part of any standard. This property originated in Internet Explorer. Apple has [a description in the Safari CSS Reference](https://developer.apple.com/library/safari/documentation/AppleApplications/Reference/SafariCSSRef/Articles/StandardCSSProperties.html#//apple_ref/doc/uid/TP30001266-SW15). Rossen Atanassov of Microsoft has [an unofficial draft specification proposal on GitHub](https://cdn.rawgit.com/atanassov/css-zoom/master/Overview.html).

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

`zoom`

1

12

No

See [bug 390936](https://bugzil.la/390936).

5.5

15

3.1

≤37

18

No

See [bug 390936](https://bugzil.la/390936).

14

3

1.0

`reset`

1-59

No

No

No

15-46

3.1

≤37-59

18-59

No

14-43

3

1.0-7.0

## See also

- [`zoom` entry in CSS-Tricks' CSS Almanac](https://css-tricks.com/almanac/properties/z/zoom/)
- The [`zoom` viewport descriptor](@viewport), for use with [`@viewport`](@viewport)
- [Bug 390936: Implement Internet Explorer `zoom` property for CSS](https://bugzilla.mozilla.org/show_bug.cgi?id=390936) on the Firefox issue tracker Bugzilla

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/zoom" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/zoom</a>
