SVGLength
=========

SVG length interface
--------------------

The `SVGLength` interface correspond to the [&lt;length&gt;](https://developer.mozilla.org/en-US/docs/Web/SVG/Content_type#length) basic data type.

An `SVGLength` object can be designated as read only, which means that attempts to modify the object will result in an exception being thrown.

### Interface overview

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td>Also implement</td><td>None</td></tr><tr class="even"><td>Methods</td><td><ul><li><code>void newValueSpecifiedUnits(in unsigned short unitType, in float valueInSpecifiedUnits)</code></li><li><code>void convertToSpecifiedUnits(in unsigned short unitType)</code></li></ul></td></tr><tr class="odd"><td>Properties</td><td><ul><li>readonly unsigned short <code>unitType</code></li><li>float <code>value</code></li><li>float <code>valueInSpecifiedUnits</code></li><li><a href="domstring"><code>DOMString</code></a> <code>valueAsString</code></li></ul></td></tr><tr class="even"><td>Constants</td><td><ul><li><code>SVG_LENGTHTYPE_UNKNOWN</code> = <code>0</code></li><li><code>SVG_LENGTHTYPE_NUMBER</code> = <code>1</code></li><li><code>SVG_LENGTHTYPE_PERCENTAGE</code> = <code>2</code></li><li><code>SVG_LENGTHTYPE_EMS</code> = <code>3</code></li><li><code>SVG_LENGTHTYPE_EXS</code> = <code>4</code></li><li><code>SVG_LENGTHTYPE_PX</code> = <code>5</code></li><li><code>SVG_LENGTHTYPE_CM</code> = <code>6</code></li><li><code>SVG_LENGTHTYPE_MM</code> = <code>7</code></li><li><code>SVG_LENGTHTYPE_IN</code> = <code>8</code></li><li><code>SVG_LENGTHTYPE_PT</code> = <code>9</code></li><li><code>SVG_LENGTHTYPE_PC</code> = <code>10</code></li></ul></td></tr><tr class="odd"><td>Normative document</td><td><a href="https://www.w3.org/TR/SVG11/types.html#InterfaceSVGLength">SVG 1.1 (2nd Edition)</a></td></tr></tbody></table>

Example
-------

    <svg height="200" onload="start();" version="1.1" width="200" xmlns="http://www.w3.org/2000/svg">
      <script type="text/javascript"><![CDATA[
    function start() {
      var rect = document.getElementById("myRect");
      var val  = rect.x.baseVal;

      // read x in pixel and cm units
      console.log("value: " + val.value +
                ", valueInSpecifiedUnits: " + val.unitType + ": " + val.valueInSpecifiedUnits +
                ", valueAsString: " + val.valueAsString);

      // set x = 20pt and read it out in pixel and pt units
      val.newValueSpecifiedUnits(SVGLength.SVG_LENGTHTYPE_PT, 20);
      console.log("value: " + val.value +
                ", valueInSpecifiedUnits " + val.unitType + ": " + val.valueInSpecifiedUnits +
                ", valueAsString: " + val.valueAsString);

      // convert x = 20pt to inches and read out in pixel and inch units
      val.convertToSpecifiedUnits(SVGLength.SVG_LENGTHTYPE_IN);
      console.log("value: " + val.value +
                ", valueInSpecifiedUnits " + val.unitType + ": " + val.valueInSpecifiedUnits +
                ", valueAsString: " + val.valueAsString);
    }
    ]]></script>
      <rect id="myRect"
            x="1cm" y="1cm"
            fill="green" stroke="black" stroke-width="1"
            width="1cm" height="1cm"
      />
    </svg>

Results on a desktop monitor (pixel units will be dpi-dependent):

    value: 37.7952766418457, valueInSpecifiedUnits: 6: 1, valueAsString: 1cm
    value: 26.66666603088379, valueInSpecifiedUnits 9: 20, valueAsString: 20pt
    value: 26.66666603088379, valueInSpecifiedUnits 8: 0.277777761220932, valueAsString: 0.277778in

Constants
---------

<table><thead><tr class="header"><th>Name</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>SVG_LENGTHTYPE_UNKNOWN</code></td><td><code>0</code></td><td>The unit type is not one of predefined unit types. It is invalid to attempt to define a new value of this type or to attempt to switch an existing value to this type.</td></tr><tr class="even"><td><code>SVG_LENGTHTYPE_NUMBER</code></td><td><code>1</code></td><td>No unit type was provided (i.e., a unitless value was specified), which indicates a value in user units.</td></tr><tr class="odd"><td><code>SVG_LENGTHTYPE_PERCENTAGE</code></td><td><code>2</code></td><td>A percentage value was specified.</td></tr><tr class="even"><td><code>SVG_LENGTHTYPE_EMS</code></td><td><code>3</code></td><td>A value was specified using the em units defined in CSS2.</td></tr><tr class="odd"><td><code>SVG_LENGTHTYPE_EXS</code></td><td><code>4</code></td><td>A value was specified using the ex units defined in CSS2.</td></tr><tr class="even"><td><code>SVG_LENGTHTYPE_PX</code></td><td><code>5</code></td><td>A value was specified using the px units defined in CSS2.</td></tr><tr class="odd"><td><code>SVG_LENGTHTYPE_CM</code></td><td><code>6</code></td><td>A value was specified using the cm units defined in CSS2.</td></tr><tr class="even"><td><code>SVG_LENGTHTYPE_MM</code></td><td><code>7</code></td><td>A value was specified using the mm units defined in CSS2.</td></tr><tr class="odd"><td><code>SVG_LENGTHTYPE_IN</code></td><td><code>8</code></td><td>A value was specified using the in units defined in CSS2.</td></tr><tr class="even"><td><code>SVG_LENGTHTYPE_PT</code></td><td><code>9</code></td><td>A value was specified using the pt units defined in CSS2.</td></tr><tr class="odd"><td><code>SVG_LENGTHTYPE_PC</code></td><td><code>10</code></td><td>A value was specified using the pc units defined in CSS2.</td></tr></tbody></table>

Properties
----------

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Name</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>unitType</code></td><td>unsigned short</td><td>The type of the value as specified by one of the <code>SVG_LENGTHTYPE_*</code> constants defined on this interface.</td></tr><tr class="even"><td><code>value</code></td><td>float</td><td><p>The value as a floating point value, in user units. Setting this attribute will cause <code>valueInSpecifiedUnits</code> and <code>valueAsString</code> to be updated automatically to reflect this setting.</p><p><strong>Exceptions on setting:</strong> a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the length corresponds to a read only attribute or when the object itself is read only.</p></td></tr><tr class="odd"><td><code>valueInSpecifiedUnits</code></td><td>float</td><td><p>The value as a floating point value, in the units expressed by <code>unitType</code>. Setting this attribute will cause <code>value</code> and <code>valueAsString</code> to be updated automatically to reflect this setting.</p><p><strong>Exceptions on setting:</strong> a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the length corresponds to a read only attribute or when the object itself is read only.</p></td></tr><tr class="even"><td><code>valueAsString</code></td><td><a href="domstring"><code>DOMString</code></a></td><td><p>The value as a string value, in the units expressed by <code>unitType</code>. Setting this attribute will cause <code>value</code>, <code>valueInSpecifiedUnits</code>, and <code>unitType</code> to be updated automatically to reflect this setting.</p><p><strong>Exceptions on setting:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>SYNTAX_ERR</code> is raised if the assigned string cannot be parsed as a valid <a href="https://developer.mozilla.org/en-US/docs/Web/SVG/Content_type#length">&lt;length&gt;</a>.</li><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the length corresponds to a read only attribute or when the object itself is read only.</li></ul></td></tr></tbody></table>

Methods
-------

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Name &amp; Arguments</th><th>Return</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>newValueSpecifiedUnits(in unsigned short unitType, in float valueInSpecifiedUnits)</code></td><td>void</td><td><p>Reset the value as a number with an associated unitType, thereby replacing the values for all of the attributes on the object.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NOT_SUPPORTED_ERR</code> is raised if <code>unitType</code> is <code>SVG_LENGTHTYPE_UNKNOWN</code> or not a valid unit type constant (one of the other <code>SVG_LENGTHTYPE_*</code> constants defined on this interface).</li><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the length corresponds to a read only attribute or when the object itself is read only.</li></ul></td></tr><tr class="even"><td><code>convertToSpecifiedUnits(in unsigned short unitType)</code></td><td>void</td><td>Preserve the same underlying stored value, but reset the stored unit identifier to the given <code>unitType</code>. Object attributes <code>unitType</code>, <code>valueInSpecifiedUnits</code>, and <code>valueAsString</code> might be modified as a result of this method. For example, if the original value were <code>"0.5cm"</code> and the method was invoked to convert to millimeters, then the <code>unitType</code> would be changed to <code>SVG_LENGTHTYPE_MM</code>, <code>valueInSpecifiedUnits</code> would be changed to the numeric value <code>5</code> and <code>valueAsString</code> would be changed to <code>"5mm"</code>.</td></tr></tbody></table>

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

`SVGLength`

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

15

3

1

18

4

14

1

1.0

`newValueSpecifiedUnits`

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

`unitType`

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

`valueAsString`

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

`valueInSpecifiedUnits`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGLength" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGLength</a>
