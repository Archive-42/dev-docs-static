SVGTransform
============

SVG transform interface
-----------------------

`SVGTransform` is the interface for one of the component transformations within an [`SVGTransformList`](svgtransformlist); thus, an `SVGTransform` object corresponds to a single component (e.g., `scale(…)` or `matrix(…)`) within a `transform` attribute.

An `SVGTransform` object can be designated as read only, which means that attempts to modify the object will result in an exception being thrown.

### Interface overview

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td>Also implement</td><td><em>None</em></td></tr><tr class="even"><td>Methods</td><td><ul><li><code>void setMatrix(in SVGMatrix</code> matrix)</li><li><code>void setTranslate(in float tx, in float ty)</code></li><li><code>void setScale(in float sx, in float sy)</code></li><li><code>void setRotate(in float angle, in float cx, in float cy)</code></li><li><code>void setSkewX(in float angle)</code></li><li><code>void setSkewY(in float angle)</code></li></ul></td></tr><tr class="odd"><td>Properties</td><td><ul><li>readonly unsigned short <code>type</code></li><li>readonly float <code>angle</code></li><li>readonly <a href="svgmatrix"><code>SVGMatrix</code></a> <code>matrix</code></li></ul></td></tr><tr class="even"><td>Constants</td><td><ul><li><code>SVG_TRANSFORM_UNKNOWN</code> = 0</li><li><code>SVG_TRANSFORM_MATRIX</code> = 1</li><li><code>SVG_TRANSFORM_TRANSLATE</code> = 2</li><li><code>SVG_TRANSFORM_SCALE</code> = 3</li><li><code>SVG_TRANSFORM_ROTATE</code> = 4</li><li><code>SVG_TRANSFORM_SKEWX</code> = 5</li><li><code>SVG_TRANSFORM_SKEWY</code> = 6</li></ul></td></tr><tr class="odd"><td>Normative document</td><td><a href="https://www.w3.org/TR/SVG11/coords.html#InterfaceSVGTransform">SVG 1.1 (2nd Edition)</a></td></tr></tbody></table>

Constants
---------

<table><thead><tr class="header"><th>Name</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>SVG_TRANSFORM_UNKNOWN</code></td><td>0</td><td>The unit type is not one of predefined unit types. It is invalid to attempt to define a new value of this type or to attempt to switch an existing value to this type.</td></tr><tr class="even"><td><code>SVG_TRANSFORM_MATRIX</code></td><td>1</td><td>A <code>matrix(…)</code> transformation</td></tr><tr class="odd"><td><code>SVG_TRANSFORM_TRANSLATE</code></td><td>2</td><td>A <code>translate(…)</code> transformation</td></tr><tr class="even"><td><code>SVG_TRANSFORM_SCALE</code></td><td>3</td><td>A <code>scale(…)</code> transformation</td></tr><tr class="odd"><td><code>SVG_TRANSFORM_ROTATE</code></td><td>4</td><td>A <code>rotate(…)</code> transformation</td></tr><tr class="even"><td><code>SVG_TRANSFORM_SKEWX</code></td><td>5</td><td>A <code>skewx(…)</code> transformation</td></tr><tr class="odd"><td><code>SVG_TRANSFORM_SKEWY</code></td><td>6</td><td>A <code>skewy(…)</code> transformation</td></tr></tbody></table>

Properties
----------

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Name</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>type</code></td><td>unsigned short</td><td>The type of the value as specified by one of the SVG_TRANSFORM_* constants defined on this interface.</td></tr><tr class="even"><td><code>angle</code></td><td>float</td><td>A convenience attribute for <code>SVG_TRANSFORM_ROTATE</code>, <code>SVG_TRANSFORM_SKEWX</code> and <code>SVG_TRANSFORM_SKEWY</code>. It holds the angle that was specified.<br />
<br />
For <code>SVG_TRANSFORM_MATRIX</code>, <code>SVG_TRANSFORM_TRANSLATE</code> and <code>SVG_TRANSFORM_SCALE</code>, <code>angle</code> will be zero.</td></tr><tr class="odd"><td><code>matrix</code></td><td><a href="svgmatrix"><code>SVGMatrix</code></a></td><td><p>The matrix that represents this transformation. The matrix object is live, meaning that any changes made to the <code>SVGTransform</code> object are immediately reflected in the matrix object and vice versa. In case the matrix object is changed directly (i.e., without using the methods on the <code>SVGTransform</code> interface itself) then the type of the <code>SVGTransform</code> changes to <code>SVG_TRANSFORM_MATRIX</code>.</p><ul><li>For <code>SVG_TRANSFORM_MATRIX</code>, the matrix contains the a, b, c, d, e, f values supplied by the user.</li><li>For <code>SVG_TRANSFORM_TRANSLATE</code>, e and f represent the translation amounts (a=1, b=0, c=0 and d=1).</li><li>For <code>SVG_TRANSFORM_SCALE</code>, a and d represent the scale amounts (b=0, c=0, e=0 and f=0).</li><li>For <code>SVG_TRANSFORM_SKEWX</code> and <code>SVG_TRANSFORM_SKEWY</code>, a, b, c and d represent the matrix which will result in the given skew (e=0 and f=0).</li><li>For <code>SVG_TRANSFORM_ROTATE</code>, a, b, c, d, e and f together represent the matrix which will result in the given rotation. When the rotation is around the center point (0, 0), e and f will be zero.</li></ul></td></tr></tbody></table>

Methods
-------

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Name &amp; Arguments</th><th>Return</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>setMatrix(in SVGMatrix</code> <em>matrix</em>)</td><td><em>void</em></td><td><p>Sets the transform type to <code>SVG_TRANSFORM_MATRIX</code>, with parameter matrix defining the new transformation. Note that the values from the parameter <code>matrix</code> are copied.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when attempting to modify a read only attribute or when the object itself is read only.</li></ul></td></tr><tr class="even"><td><code>setTranslate(in float tx , in float ty)</code></td><td><em>void</em></td><td><p>Sets the transform type to <code>SVG_TRANSFORM_TRANSLATE</code>, with parameters <code>tx</code> and <code>ty</code> defining the translation amounts.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when attempting to modify a read only attribute or when the object itself is read only.</li></ul></td></tr><tr class="odd"><td><code>setScale(in float sx , in float sy)</code></td><td><em>void</em></td><td><p>Sets the transform type to <code>SVG_TRANSFORM_SCALE</code>, with parameters <code>sx</code> and <code>sy</code> defining the scale amounts.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when attempting to modify a read only attribute or when the object itself is read only.</li></ul></td></tr><tr class="even"><td><code>setRotate(in float angle, in float cx , in float cy)</code></td><td><em>void</em></td><td><p>Sets the transform type to <code>SVG_TRANSFORM_ROTATE</code>, with parameter <code>angle</code> defining the rotation angle and parameters <code>cx</code> and <code>cy</code> defining the optional center of rotation.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when attempting to modify a read only attribute or when the object itself is read only.</li></ul></td></tr><tr class="odd"><td><code>setSkewX(in float angle)</code></td><td><em>void</em></td><td><p>Sets the transform type to <code>SVG_TRANSFORM_SKEWX</code>, with parameter <code>angle</code> defining the amount of skew.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when attempting to modify a read only attribute or when the object itself is read only.</li></ul></td></tr><tr class="even"><td><code>setSkewY(in float angle)</code></td><td><em>void</em></td><td><p>Sets the transform type to <code>SVG_TRANSFORM_SKEWY</code>, with parameter <code>angle</code> defining the amount of skew.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when attempting to modify a read only attribute or when the object itself is read only.</li></ul></td></tr></tbody></table>

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

`SVGTransform`

1

12

1.5

9

≤12.1

4

1

18

4

≤12.1

3.2

1.0

`angle`

1

12

1.5

9

15

4

1

18

4

14

3.2

1.0

`matrix`

1

12

1.5

9

15

4

1

18

4

14

3.2

1.0

`setMatrix`

1

12

1.5

9

15

4

1

18

4

14

3.2

1.0

`setRotate`

1

12

1.5

9

15

4

1

18

4

14

3.2

1.0

`setScale`

1

12

1.5

9

15

4

1

18

4

14

3.2

1.0

`setSkewX`

1

12

1.5

9

15

4

1

18

4

14

3.2

1.0

`setSkewY`

1

12

1.5

9

15

4

1

18

4

14

3.2

1.0

`setTranslate`

1

12

1.5

9

15

4

1

18

4

14

3.2

1.0

`type`

1

12

1.5

9

15

4

1

18

4

14

3.2

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGTransform" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGTransform</a>
