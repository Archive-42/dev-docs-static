# backdrop-filter

The `backdrop-filter` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property lets you apply graphical effects such as blurring or color shifting to the area behind an element. Because it applies to everything _behind_ the element, to see the effect you must make the element or its background at least partially transparent.

    /* Keyword value */
    backdrop-filter: none;

    /* URL to SVG filter */
    backdrop-filter: url(commonfilters.svg#filter);

    /* <filter-function> values */
    backdrop-filter: blur(2px);
    backdrop-filter: brightness(60%);
    backdrop-filter: contrast(40%);
    backdrop-filter: drop-shadow(4px 4px 10px blue);
    backdrop-filter: grayscale(30%);
    backdrop-filter: hue-rotate(120deg);
    backdrop-filter: invert(70%);
    backdrop-filter: opacity(20%);
    backdrop-filter: sepia(90%);
    backdrop-filter: saturate(80%);

    /* Multiple filters */
    backdrop-filter: url(filters.svg#filter) blur(4px) saturate(150%);

    /* Global values */
    backdrop-filter: inherit;
    backdrop-filter: initial;
    backdrop-filter: unset;

## Syntax

### Values

`none`  
No filter is applied to the backdrop.

`<filter-function-list>`  
A space-separated list of [`<filter-function>`](filter-function)s or an [SVG filter](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/filter) that will be applied to the backdrop.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements; In SVG, it applies to container elements excluding the <a href="https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs"><code>defs</code></a> element and all graphics elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="filter#interpolation">filter function list</a></td></tr></tbody></table>

## Formal syntax

    none | <filter-function-list>where
    <filter-function-list> = [ <filter-function> | <url> ]+where
    <filter-function> = <blur()> | <brightness()> | <contrast()> | <drop-shadow()> | <grayscale()> | <hue-rotate()> | <invert()> | <opacity()> | <saturate()> | <sepia()>where
    <blur()> = blur( <length> )
    <brightness()> = brightness( <number-percentage> )
    <contrast()> = contrast( [ <number-percentage> ] )
    <drop-shadow()> = drop-shadow( <length>{2,3} <color>? )
    <grayscale()> = grayscale( <number-percentage> )
    <hue-rotate()> = hue-rotate( <angle> )
    <invert()> = invert( <number-percentage> )
    <opacity()> = opacity( [ <number-percentage> ] )
    <saturate()> = saturate( <number-percentage> )
    <sepia()> = sepia( <number-percentage> )where
    <number-percentage> = <number> | <percentage>
    <color> = <rgb()> | <rgba()> | <hsl()> | <hsla()> | <hex-color> | <named-color> | currentcolor | <deprecated-system-color>where
    <rgb()> = rgb( <percentage>{3} [ / <alpha-value> ]? ) | rgb( <number>{3} [ / <alpha-value> ]? ) | rgb( <percentage>#{3} , <alpha-value>? ) | rgb( <number>#{3} , <alpha-value>? )
    <rgba()> = rgba( <percentage>{3} [ / <alpha-value> ]? ) | rgba( <number>{3} [ / <alpha-value> ]? ) | rgba( <percentage>#{3} , <alpha-value>? ) | rgba( <number>#{3} , <alpha-value>? )
    <hsl()> = hsl( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsl( <hue>, <percentage>, <percentage>, <alpha-value>? )
    <hsla()> = hsla( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsla( <hue>, <percentage>, <percentage>, <alpha-value>? )where
    <alpha-value> = <number> | <percentage>
    <hue> = <number> | <angle>

## Examples

### CSS

    .box {
      background-color: rgba(255, 255, 255, 0.3);
      border-radius: 5px;
      font-family: sans-serif;
      text-align: center;
      line-height: 1;
     -webkit-backdrop-filter: blur(10px);
      backdrop-filter: blur(10px);
      max-width: 50%;
      max-height: 50%;
      padding: 20px 40px;
    }

    html,
    body {
      height: 100%;
      width: 100%;
    }

    body {
      background-image: url(https://picsum.photos/id/1080/6858/4574), linear-gradient(rgb(219, 166, 166), rgb(0, 0, 172));
      background-position: center center;
      background-repeat: no-repeat;
      background-size: cover;
    }

    .container {
      align-items: center;
      display: flex;
      justify-content: center;
      height: 100%;
      width: 100%;
    }

### HTML

    <div class="container">
      <div class="box">
        <p>backdrop-filter: blur(10px)</p>
      </div>
    </div>

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/filter-effects-2/#BackdropFilterProperty">Filter Effects Module Level 2<br />
<span class="small">The definition of 'backdrop-filter' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`backdrop-filter`

76

47

17

70

No

63

34

9

76

76

47

No

See [bug 1178765](https://bugzil.la/1178765).

54

34

9

12.0

## See also

- [`filter`](filter)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/backdrop-filter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/backdrop-filter</a>
