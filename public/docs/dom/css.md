# CSS

The `CSS` interface holds useful CSS-related methods. No objects with this interface are implemented: it contains only static methods and is therefore a utilitarian interface.

## Properties

_The CSS interface is a utility interface and no object of this type can be created: only static properties are defined on it._

### Static properties

[`CSS.paintWorklet`](css/paintworklet) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="notecard inline secure">Secure context</span>  
Provides access to the Worklet responsible for all the classes related to painting.

## Methods

_The CSS interface is a utility interface and no object of this type can be created: only static methods are defined on it._

### Static methods

_No inherited static methods_.

[`CSS.registerProperty()`](css/registerproperty)  
Registers [`custom properties`](https://developer.mozilla.org/en-US/docs/Web/CSS/--*), allowing for property type checking, default values, and properties that do or do not inherit their value.

[`CSS.supports()`](css/supports)  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if the pair _property-value_, or the condition, given in parameter is supported.

[`CSS.escape()`](css/escape)  
Can be used to escape a string mostly for use as part of a CSS selector.

[`CSS factory functions`](css/factory_functions)  
Can be used to return a new `CSSUnitValue` with a value of the parameter number of the units of the name of the factory function method used.

    CSS.em(3) // CSSUnitValue {value: 3, unit: "em"}

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-paint-api-1/#dom-css-paintworklet">CSS Painting API Level 1<br />
<span class="small">The definition of 'paintWorklet' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds the <code>paintWorklet</code> static property.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/cssom/#the-css.escape()-method">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSS' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds the <code>escape()</code> static method.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/css-conditional-3/#the-css-interface">CSS Conditional Rules Module Level 3<br />
<span class="small">The definition of 'CSS' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`CSS`

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

- [Components.utils.importGlobalProperties](https://developer.mozilla.org/en-US/docs/Components.utils.importGlobalProperties)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSS" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSS</a>
