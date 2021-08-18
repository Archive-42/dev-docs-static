# CSS numeric factory functions

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The **CSS numeric factory functions**, such as `CSS.em()` and `CSS.turn()` are methods that return [CSSUnitValues](../cssunitvalue) with the value being the numeric argument and the unit being the name of the method used. These functions create new numeric values less verbosely than using the [`CSSUnitValue.CSSUnitValue()`](../cssunitvalue/cssunitvalue) constructor.

## Syntax

    CSS.number(number);
    CSS.percent(number);

    // <length>
    CSS.em(number);
    CSS.ex(number);
    CSS.ch(number);
    CSS.ic(number);
    CSS.rem(number);
    CSS.lh(number);
    CSS.rlh(number);
    CSS.vw(number);
    CSS.vh(number);
    CSS.vi(number);
    CSS.vb(number);
    CSS.vmin(number);
    CSS.vmax(number);
    CSS.cm(number);
    CSS.mm(number);
    CSS.Q(number);
    CSS.in(number);
    CSS.pt(number);
    CSS.pc(number);
    CSS.px(number);

    // <angle>
    CSS.deg(number);
    CSS.grad(number);
    CSS.rad(number);
    CSS.turn(number);

    // <time>
    CSS.s(number);
    CSS.ms(number);

    // <frequency>
    CSS.Hz(number);
    CSS.kHz(number);

    // <resolution>
    CSS.dpi(number);
    CSS.dpcm(number);
    CSS.dppx(number);

    // <flex>
    CSS.fr(number);

## Examples

We use the `CSS.vmax()` numeric factory function to create a [`CSSUnitValue`](../cssunitvalue):

    let height = CSS.vmax(50);

    console.log( height );       // CSSUnitValue {value: 50, unit: "vmax"}
    console.log( height.value )  // 50
    console.log( height.unit )   // vmax

In this example, we set the margin on our element using the` CSS.px()` factory function:

    myElement.attributeStyleMap.set('margin', CSS.px(40));
    let currentMargin = myElement.attributeStyleMap.get('margin');
    console.log(currentMargin.value, currentMargin.unit); // 40, 'px'

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#numeric-factory">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'Numeric Factory Functions' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`factory_functions`

28

12

22

No

12.1

10

4.4

28

22

12.1

Yes

1.5

`Hz`

66

79

No

No

53

No

66

66

No

47

No

9.0

`Q`

66

79

No

No

53

No

66

66

No

47

No

9.0

`ch`

66

79

No

No

53

No

66

66

No

47

No

9.0

`cm`

66

79

No

No

53

No

66

66

No

47

No

9.0

`deg`

66

79

No

No

53

No

66

66

No

47

No

9.0

`dpcm`

66

79

No

No

53

No

66

66

No

47

No

9.0

`dpi`

66

79

No

No

53

No

66

66

No

47

No

9.0

`dppx`

66

79

No

No

53

No

66

66

No

47

No

9.0

`em`

66

79

No

No

53

No

66

66

No

47

No

9.0

`escape`

46

79

31

No

33

10

46

46

31

33

10

5.0

`ex`

66

79

No

No

53

No

66

66

No

47

No

9.0

`fr`

66

79

No

No

53

No

66

66

No

47

No

9.0

`grad`

66

79

No

No

53

No

66

66

No

47

No

9.0

`ic`

No

See [bug 778495](https://crbug.com/778495)

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

`in`

66

79

No

No

53

No

66

66

No

47

No

9.0

`kHz`

66

79

No

No

53

No

66

66

No

47

No

9.0

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

`mm`

66

79

No

No

53

No

66

66

No

47

No

9.0

`ms`

66

79

No

No

53

No

66

66

No

47

No

9.0

`number`

66

79

No

No

53

No

66

66

No

47

No

9.0

`paintWorklet`

65

79

No

No

52

No

65

65

No

47

No

9.0

`pc`

66

79

No

No

53

No

66

66

No

47

No

9.0

`percent`

66

79

No

No

53

No

66

66

No

47

No

9.0

`pt`

66

79

No

No

53

No

66

66

No

47

No

9.0

`px`

66

79

No

No

53

No

66

66

No

47

No

9.0

`rad`

66

79

No

No

53

No

66

66

No

47

No

9.0

`registerProperty`

78

79

No

No

65

No

78

78

No

No

No

12.0

`rem`

66

79

No

No

53

No

66

66

No

47

No

9.0

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

`s`

66

79

No

No

53

No

66

66

No

47

No

9.0

`supports`

61

28

Version 60 or older didn't support parentheses-less one-argument version.

12

Edge doesn't support parentheses-less one-argument version.

55

22

Version 54 or older didn't support parentheses-less one-argument version.

No

12.1

10

61

37

Version 60 or older didn't support parentheses-less one-argument version.

61

28

Version 60 or older didn't support parentheses-less one-argument version.

55

22

Version 54 or older didn't support parentheses-less one-argument version.

12.1

Yes

8.0

1.5

Samsung Internet 8.0 or older didn't support parentheses-less one-argument version.

`turn`

66

79

No

No

53

No

66

66

No

47

No

9.0

`vb`

No

See [bug 778495](https://crbug.com/778495)

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

66

79

No

No

53

No

66

66

No

47

No

9.0

`vi`

No

See [bug 778495](https://crbug.com/778495)

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

66

79

No

No

53

No

66

66

No

47

No

9.0

`vmin`

66

79

No

No

53

No

66

66

No

47

No

9.0

`vw`

66

79

No

No

53

No

66

66

No

47

No

9.0

## See also

- [`CSSUnitValue.CSSUnitValue()`](../cssunitvalue/cssunitvalue)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSS/factory_functions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSS/factory_functions</a>
