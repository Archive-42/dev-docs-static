SVGNumber
=========

The `SVGNumber` interface corresponds to the [`<number>`](https://developer.mozilla.org/en-US/docs/Web/CSS/number) basic data type.

An `SVGNumber` object can be designated as read only, which means that attempts to modify the object will result in an exception being thrown.

Properties
----------

<span class="page-not-created">`SVGNumber.value`</span>  
A float representing the number.

Note: If the `SVGNumber` is read-only, a [`DOMException`](domexception) with the code NO\_MODIFICATION\_ALLOWED\_ERR is raised on an attempt to change the value.

Methods
-------

*This interface doesn't provide any specific methods.*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/types.html#InterfaceSVGNumber">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'SVGNumber' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/types.html#InterfaceSVGNumber">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGNumber' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGNumber`

1

12

1.5

9

≤12.1

3

≤37

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

15

3

1

18

4

14

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGNumber" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGNumber</a>
