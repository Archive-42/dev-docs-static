# &lt;length&gt;

The `<length>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types) represents a distance value. Lengths can be used in numerous CSS properties, such as [`width`](width), [`height`](height), [`margin`](margin), [`padding`](padding), [`border-width`](border-width), [`font-size`](font-size), and [`text-shadow`](text-shadow).

**Note:** Although [`<percentage>`](percentage) values are usable in some of the same properties that accept `<length>` values, they are not themselves `<length>` values. See [`<length-percentage>`](length-percentage).

## Syntax

The `<length>` data type consists of a [`<number>`](number) followed by one of the units listed below. As with all CSS dimensions, there is no space between the unit literal and the number. The length unit is optional after the number `0`.

**Note:** Some properties allow negative `<length>`s, while others do not.

### Units

#### Relative length units

Relative lengths represent a measurement in terms of some other distance. Depending on the unit, this can be the size of a specific character, the [line height](line-height), or the size of the [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport).

##### Font-relative lengths

Font-relative lengths define the `<length>` value in terms of the size of a particular character or font attribute in the font currently in effect in an element or its parent.

**Note:** These units, especially `em` and `rem`, are often used to create scalable layouts, which maintain the [vertical rhythm of the page](https://24ways.org/2006/compose-to-a-vertical-rhythm) even when the user changes the font size.

`cap` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Represents the "cap height" (nominal height of capital letters) of the element’s [`font`](font).

`ch`  
Represents the width, or more precisely the advance measure, of the glyph "0" (zero, the Unicode character U+0030) in the element's [`font`](font).

In the cases where it is impossible or impractical to determine the measure of the “0” glyph, it must be assumed to be 0.5em wide by 1em tall.

`em`  
Represents the calculated [`font-size`](font-size) of the element. If used on the [`font-size`](font-size) property itself, it represents the _inherited_ font-size of the element.

`ex`  
Represents the [x-height](https://en.wikipedia.org/wiki/X-height) of the element's [`font`](font). On fonts with the "x" letter, this is generally the height of lowercase letters in the font; `1ex ≈ 0.5em` in many fonts.

`ic` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Equal to the used advance measure of the "水" glyph (CJK water ideograph, U+6C34), found in the font used to render it.

`lh` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Equal to the computed value of the [`line-height`](line-height) property of the element on which it is used, converted to an absolute length.

`rem`  
Represents the [`font-size`](font-size) of the root element (typically [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html)). When used within the root element [`font-size`](font-size), it represents its initial value (a common browser default is `16px`, but user-defined preferences may modify this).

`rlh` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Equal to the computed value of the [`line-height`](line-height) property on the root element (typically [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html)), converted to an absolute length. When used on the [`font-size`](font-size) or [`line-height`](line-height) properties of the root element, it refers to the properties' initial value.

##### Viewport-percentage lengths

Viewport-percentage lengths define the `<length>` value relative to the size of the [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport), i.e., the visible portion of the document. Viewport lengths are invalid in [`@page`](@page) declaration blocks.

`vh`  
Equal to 1% of the height of the viewport's initial [containing block](containing_block).

`vw`  
Equal to 1% of the width of the viewport's initial [containing block](containing_block).

`vi` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Equal to 1% of the size of the initial [containing block](containing_block), in the direction of the root element’s [inline axis](css_logical_properties#inline-dimension).

`vb` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Equal to 1% of the size of the initial [containing block](containing_block), in the direction of the root element’s [block axis](css_logical_properties#block-dimension).

`vmin`  
Equal to the smaller of `vw` and `vh`.

`vmax`  
Equal to the larger of `vw` and `vh`.

#### Absolute length units

Absolute length units represent a physical measurement when the physical properties of the output medium are known, such as for print layout. This is done by anchoring one of the units to a physical unit, and then defining the others relative to it. The anchor is done differently for low-resolution devices, such as screens, versus high-resolution devices, such as printers.

For low-dpi devices, the unit `px` represents the physical _reference pixel_; other units are defined relative to it. Thus, `1in` is defined as `96px`, which equals `72pt`. The consequence of this definition is that on such devices, dimensions described in inches (`in`), centimeters (`cm`), or millimeters (`mm`) don't necessary match the size of the physical unit with the same name.

For high-dpi devices, inches (`in`), centimeters (`cm`), and millimeters (`mm`) are the same as their physical counterparts. Therefore, the `px` unit is defined relative to them (1/96 of 1 inch).

**Note:** Many users increase their [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)'s default font size to make text more legible. Absolute lengths can cause accessibility problems, since they are fixed and do not scale according to user settings. For this reason, prefer relative lengths (such as `em` or `rem`) when setting `font-size`.

`px`  
One pixel. For screen displays, it traditionally represents one device pixel (dot). However, for _printers_ and _high-resolution screens_, one CSS pixel implies multiple device pixels. `1px` = 1/96th of `1in`.

`cm`  
One centimeter. `1cm` = `96px/2.54`.

`mm`  
One millimeter. `1mm` = 1/10th of `1cm`.

`Q` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
One quarter of a millimeter. `1Q` = 1/40th of `1cm`.

`in`  
One inch. `1in` = `2.54cm` = `96px`.

`pc`  
One pica. `1pc` = `12pt` = 1/6th of `1in`.

`pt`  
One point. `1pt` = 1/72nd of `1in`.

`mozmm` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>, removed in Firefox 59  
An experimental unit that attempts to render at exactly one millimeter regardless of the size or resolution of the display. This is rarely actually what you want, but may be useful in particular for mobile devices.

## Interpolation

When animated, values of the `<length>` data type are interpolated as real, floating-point numbers. The interpolation happens on the calculated value. The speed of the interpolation is determined by the [timing function](easing-function) associated with the animation.

## Examples

### Length unit comparison

The following demo provides you with an input field in which you can enter a `<length>` value (e.g. `300px`, `50%`, `30vw`) to set the width of a result bar that will appear below it once you've pressed Return.

This allows you to compare and contrast the effect of different length units.

#### HTML

    <div class="outer">
      <div class="input-container">
        <label>Enter width:</label>
        <input type="text" id="length">
      </div>
      <div class="inner">

      </div>
    </div>
    <div class="results">
    </div>

#### CSS

    html {
      font-family: sans-serif;
      font-weight: bold;
      box-sizing: border-box;
    }

    .outer {
      width: 100%;
      height: 50px;
      background-color: #eee;
      position: relative;
    }

    .inner {
      height: 50px;
      background-color: #999;
      box-shadow: inset 3px 3px 5px rgba(255,255,255,0.5),
                  inset -3px -3px 5px rgba(0,0,0,0.5);
    }

    .result {
      height: 20px;
      background-color: #999;
      box-shadow: inset 3px 3px 5px rgba(255,255,255,0.5),
                  inset -3px -3px 5px rgba(0,0,0,0.5);
      background-color: orange;
      display: flex;
      align-items: center;
      margin-top: 10px;
    }

    .result code {
      position: absolute;
      margin-left: 20px;
    }

    .results {
      margin-top: 10px;
    }

    .input-container {
      position: absolute;
      display: flex;
      justify-content: flex-start;
      align-items: center;
      height: 50px;
    }

    label {
      margin: 0 10px 0 20px;
    }

#### JavaScript

    const inputDiv = document.querySelector('.inner');
    const inputElem = document.querySelector('input');
    const resultsDiv = document.querySelector('.results');

    inputElem.addEventListener('change', () => {
      inputDiv.style.width = inputElem.value;

      const result = document.createElement('div');
      result.className = 'result';
      result.style.width = inputElem.value;
      result.innerHTML = `<code>width: ${inputElem.value}</code>`;
      resultsDiv.appendChild(result);

      inputElem.value = '';
      inputElem.focus();
    })

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-values-4/#lengths">CSS Values and Units Module Level 4<br />
<span class="small">The definition of '&lt;length&gt;' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Adds the <code>vi</code>, <code>vb</code>, <code>ic</code>, <code>lh</code>, and <code>rlh</code> units.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-values-3/#lengths">CSS Values and Units Module Level 3<br />
<span class="small">The definition of '&lt;length&gt;' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Adds the <code>ch</code>, <code>rem</code>, <code>vw</code>, <code>vh</code>, <code>vmin</code>, <code>vmax</code>, and <code>Q</code> units.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/syndata.html#length-units">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of '&lt;length&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Explicit definition of the <code>em</code>, <code>pt</code>, <code>pc</code>, and <code>px</code> units.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#length-units">CSS Level 1<br />
<span class="small">The definition of '&lt;length&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition. Implicit definition of the <code>em</code>, <code>pt</code>, <code>pc</code>, and <code>px</code> units.</td></tr></tbody></table>

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

`length`

1

12

1

3

3.5

1

≤37

18

4

10.1

1

1.0

`Q`

63

79

49

No

50

No

63

63

49

46

No

8.0

`cap`

No

No

No

No

No

No

No

No

No

No

No

No

`ch`

27

12

1

\["From Firefox 1 to Firefox 3, `ch` was the width of the _M_ character.", "From Firefox 1 to Firefox 3, `ch` did not work with [`border-width`](https://developer.mozilla.org/docs/Web/CSS/border-width) and [`outline-width`](https://developer.mozilla.org/docs/Web/CSS/outline-width) CSS properties."\]

9

20

7

≤37

27

4

14

7

1.5

`ex`

1

12

1

4

3.5

1

1

18

4

10.1

1

1.0

`ic`

No

No

No

See [bug 1531223](https://bugzil.la/1531223)

No

No

No

See [bug 195176](https://webkit.org/b/195176)

No

No

No

No

No

No

`lh`

No

See [bug 937104](https://crbug.com/937104)

No

No

See [bug 1310170](https://bugzil.la/1310170)

No

No

No

No

No

No

No

No

No

`mozmm`

No

No

4-59

No

No

No

No

No

4-59

No

No

No

`rem`

4

12

3.6

9

11.6

5

2

18

4

12

4

1.0

`rlh`

No

See [bug 937104](https://crbug.com/937104)

No

No

See [bug 1310170](https://bugzil.la/1310170)

No

No

No

No

No

No

No

No

No

`vb`

No

No

No

See [bug 1287034](https://bugzil.la/1287034)

No

No

No

See [bug 159801](https://webkit.org/b/159801)

No

No

No

No

No

No

`vh`

20

12

19

Starting with version 21, viewport-percentage lengths are invalid in `@page`.

9

20

6

≤37

25

19

Starting with version 21, viewport-percentage lengths are invalid in `@page`.

14

6

1.5

`vi`

No

No

No

See [bug 1287034](https://bugzil.la/1287034)

No

No

No

See [bug 159801](https://webkit.org/b/159801)

No

No

No

No

No

No

`vmax`

26

16

19

Starting with version 21, viewport-percentage lengths are invalid in `@page`.

No

15

6.1

1.5

26

19

Starting with version 21, viewport-percentage lengths are invalid in `@page`.

14

6.1

1.5

`vmin`

26

12

12

19

Starting with version 21, viewport-percentage lengths are invalid in `@page`.

10

9

15

6.1

≤37

26

19

Starting with version 21, viewport-percentage lengths are invalid in `@page`.

14

6.1

1.5

`vw`

20

12

19

Starting with version 21, viewport-percentage lengths are invalid in `@page`.

9

20

6

≤37

25

19

Starting with version 21, viewport-percentage lengths are invalid in `@page`.

14

6

1.5

## See also

- [CSS values & units tutorial](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units)
- [CSS values & units reference](css_values_and_units)
- [Box Model](css_box_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/length" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/length</a>
