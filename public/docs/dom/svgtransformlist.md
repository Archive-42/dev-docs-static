SVGTransformList
================

SVG transform list interface
----------------------------

The `SVGTransformList` defines a list of [`SVGTransform`](svgtransform) objects.

An `SVGTransformList` object can be designated as read only, which means that attempts to modify the object will result in an exception being thrown.

**Note:** Starting in Gecko 9.0,the `SVGTransformList` DOM interface is now indexable and can be accessed like Arrays

### Interface overview

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td>Also implement</td><td><em>None</em></td></tr><tr class="even"><td>Methods</td><td><ul><li><code>void clear()</code></li><li><a href="svgtransform"><code>SVGTransform</code></a> <code>initialize(in SVGTransform</code> <em>newItem</em>)</li><li><a href="svgtransform"><code>SVGTransform</code></a> <code>getItem(in unsigned long index)</code></li><li><a href="svgtransform"><code>SVGTransform</code></a> <code>insertItemBefore(in SVGTransform</code> <em>newItem</em>, in unsigned long <em>index</em>)</li><li><a href="svgtransform"><code>SVGTransform</code></a> <code>replaceItem(in SVGTransform</code> <em>newItem</em>, in unsigned long <em>index</em>)</li><li><a href="svgtransform"><code>SVGTransform</code></a> <code>removeItem(in unsigned long index)</code></li><li><a href="svgtransform"><code>SVGTransform</code></a> <code>appendItem(in SVGTransform</code> <em>newItem</em>)</li><li><a href="svgtransform"><code>SVGTransform</code></a> <code>createSVGTransformFromMatrix(in SVGMatrix</code>)</li><li><a href="svgtransform"><code>SVGTransform</code></a> <code>consolidate()</code></li></ul></td></tr><tr class="odd"><td>Properties</td><td><ul><li>readonly unsigned long <code>numberOfItems</code></li><li>readonly unsigned long <code>length</code> <span class="icon non-standard" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This API has not been standardized. </span></li></ul></td></tr><tr class="even"><td>Normative document</td><td><a href="https://www.w3.org/TR/SVG/coords.html#InterfaceSVGTransformList">SVG 1.1 (2nd Edition)</a></td></tr></tbody></table>

Properties
----------

<table><thead><tr class="header"><th>Name</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>numberOfItems</code></td><td>unsigned long</td><td>The number of items in the list.</td></tr><tr class="even"><td><code>length </code> <span class="icon non-standard" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This API has not been standardized. </span></td><td>unsigned long</td><td>The number of items in the list.</td></tr></tbody></table>

Methods
-------

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Name &amp; Arguments</th><th>Return</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>clear()</code></td><td><code>void</code></td><td><p>Clears all existing current items from the list, with the result being an empty list.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the list corresponds to a read only attribute or when the object itself is read only.</li></ul></td></tr><tr class="even"><td><code>initialize(in SVGTransform</code> <em>newItem</em>)</td><td><a href="svgtransform"><code>SVGTransform</code></a></td><td><p>Clears all existing current items from the list and re-initializes the list to hold the single item specified by the parameter. If the inserted item is already in a list, it is removed from its previous list before it is inserted into this list. The inserted item is the item itself and not a copy. The return value is the item inserted into the list.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the list corresponds to a read only attribute or when the object itself is read only.</li></ul></td></tr><tr class="odd"><td><code>getItem(in unsigned long index)</code></td><td><a href="svgtransform"><code>SVGTransform</code></a></td><td><p>Returns the specified item from the list. The returned item is the item itself and not a copy. Any changes made to the item are immediately reflected in the list. The first item is number 0.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the list corresponds to a read only attribute or when the object itself is read only.</li></ul></td></tr><tr class="even"><td><code>insertItemBefore(in SVGTransform</code> <em>newItem</em>, in unsigned long <em>index</em>)</td><td><a href="svgtransform"><code>SVGTransform</code></a></td><td><p>Inserts a new item into the list at the specified position. The first item is number 0. If <code>newItem</code> is already in a list, it is removed from its previous list before it is inserted into this list. The inserted item is the item itself and not a copy. If the item is already in this list, note that the index of the item to insert before is before the removal of the item. If the <code>index</code> is equal to 0, then the new item is inserted at the front of the list. If the index is greater than or equal to <code>numberOfItems</code>, then the new item is appended to the end of the list.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the list corresponds to a read only attribute or when the object itself is read only.</li></ul></td></tr><tr class="odd"><td><code>replaceItem(in SVGTransform</code> <em>newItem</em>, in unsigned long <em>index</em>)</td><td><a href="svgtransform"><code>SVGTransform</code></a></td><td><p>Replaces an existing item in the list with a new item. If <code>newItem</code> is already in a list, it is removed from its previous list before it is inserted into this list. The inserted item is the item itself and not a copy. If the item is already in this list, note that the index of the item to replace is before the removal of the item.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the list corresponds to a read only attribute or when the object itself is read only.</li><li>a <a href="domexception"><code>DOMException</code></a> with code <code>INDEX_SIZE_ERR</code> is raised if the index number is greater than or equal to <code>numberOfItems</code>.</li></ul></td></tr><tr class="even"><td><code>removeItem(in unsigned long index)</code></td><td><a href="svgtransform"><code>SVGTransform</code></a></td><td><p>Removes an existing item from the list.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the list corresponds to a read only attribute or when the object itself is read only.</li><li>a <a href="domexception"><code>DOMException</code></a> with code <code>INDEX_SIZE_ERR</code> is raised if the index number is greater than or equal to <code>numberOfItems</code>.</li></ul></td></tr><tr class="odd"><td><code>appendItem(in SVGTransform</code> <em>newItem</em>)</td><td><a href="svgtransform"><code>SVGTransform</code></a></td><td><p>Inserts a new item at the end of the list. If <code>newItem</code> is already in a list, it is removed from its previous list before it is inserted into this list. The inserted item is the item itself and not a copy.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the list corresponds to a read only attribute or when the object itself is read only.</li></ul></td></tr><tr class="even"><td><code>createSVGTransformFromMatrix(in SVGMatrix</code>)</td><td><a href="svgtransform"><code>SVGTransform</code></a></td><td>Creates an <code>SVGTransform</code> object which is initialized to transform of type <code>SVG_TRANSFORM_MATRIX</code> and whose values are the given matrix. The values from the parameter matrix are copied, the matrix parameter is not adopted as <code>SVGTransform::matrix</code>.</td></tr><tr class="odd"><td><code>consolidate()</code></td><td><a href="svgtransform"><code>SVGTransform</code></a></td><td><p>Consolidates the list of separate <code>SVGTransform</code> objects by multiplying the equivalent transformation matrices together to result in a list consisting of a single <code>SVGTransform</code> object of type <code>SVG_TRANSFORM_MATRIX</code>. The consolidation operation creates new <code>SVGTransform</code> object as the first and only item in the list. The returned item is the item itself and not a copy. Any changes made to the item are immediately reflected in the list.</p><p><strong>Exceptions:</strong></p><ul><li>a <a href="domexception"><code>DOMException</code></a> with code <code>NO_MODIFICATION_ALLOWED_ERR</code> is raised when the list corresponds to a read only attribute or when the object itself is read only.</li></ul></td></tr></tbody></table>

Examples
--------

### Using multiple SVGTransform objects

In this example we create a function that will apply three different transformations to the SVG element that has been clicked on. In order to do this we create a separate [`SVGTransform`](svgtransform) object for each transformation -- such as `translate`, `rotate`, and `scale`. We apply multiple transformation by appending the transform object to the `SVGTransformList` associated with an SVG element.

    <svg id="my-svg" viewBox="0 0 300 280"
         xmlns="http://www.w3.org/2000/svg" version="1.1">
      <desc>Example showing how to transform svg elements that using SVGTransform objects</desc>
      <script type="application/ecmascript"><![CDATA[
        function transformMe(evt) {
          // svg root element to access the createSVGTransform() function
          var svgroot = evt.target.parentNode;

          // SVGTransformList of the element that has been clicked on
          var tfmList = evt.target.transform.baseVal;

          // Create a separate transform object for each transform
          var translate = svgroot.createSVGTransform();
          translate.setTranslate(50,5);

          var rotate = svgroot.createSVGTransform();
          rotate.setRotate(10,0,0);

          var scale = svgroot.createSVGTransform();
          scale.setScale(0.8,0.8);

          // apply the transformations by appending the SVGTransform objects to the SVGTransformList associated with the element
          tfmList.appendItem(translate);
          tfmList.appendItem(rotate);
          tfmList.appendItem(scale);
        }
      ]]></script>

      <polygon fill="orange" stroke="black" stroke-width="5"
               points="100,225 100,115 130,115 70,15 70,15 10,115 40,115 40,225"
               onclick="transformMe(evt)"/>
      <rect x="200" y="100" width="100" height="100"
            fill="yellow" stroke="black" stroke-width="5"
            onclick="transformMe(evt)"/>
      <text x="40" y="250"
            font-family="Verdana" font-size="16" fill="green" >
        Click on a shape to transform it
      </text>
    </svg>

Live preview:

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/coords.html#InterfaceSVGTransformList">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'SVGTransformList' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/coords.html#InterfaceSVGTransformList">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGTransformList' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGTransformList`

5

12

1.5

9

15

5

≤37

18

4

14

4

1.0

`length`

Yes

≤79

9

No

Yes

Yes

Yes

Yes

9

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGTransformList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGTransformList</a>
