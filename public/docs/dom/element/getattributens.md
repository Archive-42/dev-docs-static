Element.getAttributeNS()
========================

The `getAttributeNS()` method of the [`Element`](../element) interface returns the string value of the attribute with the specified namespace and name. If the named attribute does not exist, the value returned will either be `null` or `""` (the empty string); see [Notes](#notes) for details.

Syntax
------

    attrVal = element.getAttributeNS(namespace, name)

### Parameters

`namespace`  
The namespace in which to look for the specified attribute.

`name`  
The name of the attribute to look for.

### Return value

The string value of the specified attribute. If the attribute doesn't exist, the result is `null`.

**Note:** Earlier versions of the DOM specification had this method described as returning an empty string for non-existent attributes, but it was not typically implemented this way since null makes more sense. The DOM4 specification now says this method should return null for non-existent attributes.

Examples
--------

The following SVG document reads the value of the `foo` attribute in a custom namespace.

    <svg xmlns="http://www.w3.org/2000/svg"
        xmlns:test="http://www.example.com/2014/test" width="40" height="40">

      <circle id="target" cx="12" cy="12" r="10" stroke="#444"
          stroke-width="2" fill="none" test:foo="Hello namespaced attribute!"/>

      <script type="text/javascript">
        var ns = 'http://www.example.com/2014/test';
        var circle = document.getElementById( 'target' );

        console.log( 'attribute test:foo: "' + circle.getAttributeNS( ns, 'foo' ) + '"' );
      </script>
    </svg>

In an HTML5 document the attribute has to be accessed with `test:foo` since namespaces are not supported.

    <!DOCTYPE html>
    <html>
    <body>

    <svg xmlns="http://www.w3.org/2000/svg"
        xmlns:test="http://www.example.com/2014/test" width="40" height="40">
      <circle id="target" cx="12" cy="12" r="10" stroke="#444" stroke-width="2"
          fill="none" test:foo="Foo value"/>
    </svg>

    <script type="text/javascript">
      var ns = 'http://www.example.com/2014/test';
      var circle = document.getElementById( 'target' );
      console.log('Attribute value: ' + circle.getAttribute('test:foo'));
    </script>

    </body>
    </html>

Notes
-----

Namespaces are only supported in XML documents. HTML5 documents have to use `getAttribute()` instead.

`getAttributeNS()` differs from [`getAttribute()`](getattribute) in that it allows you to further specify the requested attribute as being part of a particular namespace, as in the example above, where the attribute is part of the fictional "specialspace" namespace on Mozilla.

Prior to the DOM4 specification, this method was specified to return an empty string rather than null for non-existent attributes. However, most browsers instead returned null. Starting with DOM4, the specification now says to return null. However, some older browsers return an empty string. For that reason, you should use [`hasAttributeNS()`](hasattributens) to check for an attribute's existence prior to calling `getAttributeNS()` if it is possible that the requested attribute does not exist on the specified element.

DOM methods dealing with element's attributes:

<table><thead><tr class="header"><th>Not namespace-aware, most commonly used methods</th><th>Namespace-aware variants (DOM Level 2)</th><th>DOM Level 1 methods for dealing with <code>Attr</code> nodes directly (seldom used)</th><th>DOM Level 2 namespace-aware methods for dealing with <code>Attr</code> nodes directly (seldom used)</th></tr></thead><tbody><tr class="odd"><td><a href="setattribute"><code>setAttribute</code></a> (DOM 1)</td><td><a href="setattributens"><code>setAttributeNS</code></a></td><td><a href="setattributenode"><code>setAttributeNode</code></a></td><td><a href="setattributenodens"><code>setAttributeNodeNS</code></a></td></tr><tr class="even"><td><a href="getattribute"><code>getAttribute</code></a> (DOM 1)</td><td><a href="getattributens"><code>getAttributeNS</code></a></td><td><a href="getattributenode"><code>getAttributeNode</code></a></td><td><a href="getattributenodens"><code>getAttributeNodeNS</code></a></td></tr><tr class="odd"><td><a href="hasattribute"><code>hasAttribute</code></a> (DOM 2)</td><td><a href="hasattributens"><code>hasAttributeNS</code></a></td><td>-</td><td>-</td></tr><tr class="even"><td><a href="removeattribute"><code>removeAttribute</code></a> (DOM 1)</td><td><a href="removeattributens"><code>removeAttributeNS</code></a></td><td><a href="removeattributenode"><code>removeAttributeNode</code></a></td><td>-</td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-getattributens">DOM<br />
<span class="small">The definition of 'Element.getAttributeNS()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/#ID-ElGetAttrNS">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Element.getAttributeNS()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Specifies that a <code>NOT_SUPPORTED_ERR</code> exception is thrown if the UA does not support the <code>"XML"</code> feature. Also specifies that <code>null</code> must be passed to have no namespace.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/#ID-ElGetAttrNS">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Element.getAttributeNS()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`getAttributeNS`

1

12

1

Starting in Firefox 13, `null` is always returned instead of the empty string, as per the DOM4 specification. Previously, there were cases in which an empty string could be returned.

9

≤12.1

1

1

18

4

Starting in Firefox 13, `null` is always returned instead of the empty string, as per the DOM4 specification. Previously, there were cases in which an empty string could be returned.

≤12.1

1

1.0

See also
--------

-   [Code snippets:getAttributeNS](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/Code_snippets/getAttributeNS)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttributeNS" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttributeNS</a>
