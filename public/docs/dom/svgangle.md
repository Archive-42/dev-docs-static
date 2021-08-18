SVGAngle
========

Constants
---------

The `SVGAngle` interface is used to represent a value that can be an [`<angle>`](https://developer.mozilla.org/en-US/docs/Web/CSS/angle) or [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number) value. An `SVGAngle` reflected through the `animVal` attribute is always read only.

An `SVGAngle` object can be designated as read only, which means that attempts to modify the object will result in an exception being thrown.

An `SVGAngle` object can be associated with a particular element. The associated element is used to determine which element's content attribute to update if the object reflects an attribute. Unless otherwise described, an `SVGAngle` object is not associated with any element.

Every `SVGAngle` object operates in one of two modes:

1.  ***Reflect the base value*** of a reflected animatable attribute (being exposed through the `baseVal` member of an [`SVGAnimatedAngle`](svganimatedangle)),
2.  ***Be detached*,** which is the case for `SVGAngle` objects created with <span class="page-not-created">`SVGSVGElement.createSVGAngle()`</span>.

`SVG_ANGLETYPE_UNKNOWN`  
Some unknown type of value.

`SVG_ANGLETYPE_UNSPECIFIED`  
A unitless [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number) interpreted as a value in degrees.

`SVG_ANGLETYPE_DEG`  
An [`<angle>`](https://developer.mozilla.org/en-US/docs/Web/CSS/angle) with a `deg` unit.

`SVG_ANGLETYPE_RAD`  
An [`<angle>`](https://developer.mozilla.org/en-US/docs/Web/CSS/angle) with a `rad` unit.

`SVG_ANGLETYPE_GRAD`  
An [`<angle>`](https://developer.mozilla.org/en-US/docs/Web/CSS/angle) with a `grad` unit.

Properties
----------

`unitType`  
The type of the value as specified by one of the `SVG_ANGLETYPE_*` constants defined on this interface.

`value`  
The value as a floating point value, in user units. Setting this attribute will cause `valueInSpecifiedUnits` and `valueAsString` to be updated automatically to reflect this setting.

**Exceptions on setting:** A [`DOMException`](domexception) with code `NO_MODIFICATION_ALLOWED_ERR` is raised when the length corresponds to a read-only attribute, or when the object itself is read-only.

`valueInSpecifiedUnits`  
The value as a floating point value, in the units expressed by `unitType`. Setting this attribute will cause `value` and `valueAsString` to be updated automatically to reflect this setting.

**Exceptions on setting:** A [`DOMException`](domexception) with code `NO_MODIFICATION_ALLOWED_ERR` is raised when the length corresponds to a read-only attribute, or when the object itself is read-only.

`valueAsString`  
The value as a [`DOMString`](domstring) value, in the units expressed by `unitType`. Setting this attribute will cause `value`, `valueInSpecifiedUnits`, and `unitType` to be updated automatically to reflect this setting.

**Exceptions on setting:**

A [`DOMException`](domexception) with code `SYNTAX_ERR` is raised if the assigned string cannot be parsed as a valid [`<angle>`](https://developer.mozilla.org/en-US/docs/Web/CSS/angle).

A [`DOMException`](domexception) with code `NO_MODIFICATION_ALLOWED_ERR` is raised when the length corresponds to a read-only attribute, or when the object itself is read-only.

Methods
-------

`newValueSpecifiedUnits`  
Reset the value as a number with an associated unitType, thereby replacing the values for all of the attributes on the object.

**Exceptions:**

A [`DOMException`](domexception) with code `NOT_SUPPORTED_ERR` is raised if `unitType` is `SVG_ANGLETYPE_UNKNOWN` or not a valid unit type constant (one of the other `SVG_ANGLETYPE_*` constants defined on this interface).

A [`DOMException`](domexception) with code `NO_MODIFICATION_ALLOWED_ERR` is raised when the length corresponds to a read only attribute or when the object itself is read only.

`convertToSpecifiedUnits`  
Preserve the same underlying stored value, but reset the stored unit identifier to the given `unitType`. Object attributes `unitType`, `valueInSpecifiedUnits`, and `valueAsString` might be modified as a result of this method.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/types.html#InterfaceSVGAngle">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'SVGElement' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Adds the <a href="htmlorforeignelement/dataset"><code>dataset</code></a> property.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/types.html#InterfaceSVGAngle">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

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

`SVGAngle`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`convertToSpecifiedUnits`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`newValueSpecifiedUnits`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`unitType`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`value`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`valueAsString`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`valueInSpecifiedUnits`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGAngle" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGAngle</a>
