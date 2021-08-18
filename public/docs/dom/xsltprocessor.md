XSLTProcessor
=============

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

An `XSLTProcessor` applies an [XSLT](https://developer.mozilla.org/en-US/docs/Web/XSLT) stylesheet transformation to an XML document to produce a new XML document as output. It has methods to load the XSLT stylesheet, to manipulate `<xsl:param>` parameter values, and to apply the transformation to documents.

Syntax
------

The constructor has no parameters.

    new XSLTProcessor()

Methods
-------

 `[Throws] void `<span class="page-not-created">`XSLTProcessor.importStylesheet`</span>`(`[`Node`](node)` styleSheet)`   
Imports the XSLT stylesheet. If the given node is a document node, you can pass in a full XSL Transform or a [literal result element transform](https://www.w3.org/TR/xslt#result-element-stylesheet); otherwise, it must be an `<xsl:stylesheet>` or `<xsl:transform>` element.

 `[Throws] `[`DocumentFragment`](documentfragment) <span class="page-not-created">`XSLTProcessor.transformToFragment`</span>`(`[`Node`](node)` source, `[`Document`](document)` owner)`   
Transforms the node source by applying the stylesheet imported using the <span class="page-not-created">`XSLTProcessor.importStylesheet()`</span> function. The owner document of the resulting document fragment is the owner node.

 `[Throws]` [`Document`](document) <span class="page-not-created">`XSLTProcessor.transformToDocument`</span>`(`[`Node`](node)` source)`   
Transforms the node source applying the stylesheet given importing using the <span class="page-not-created">`XSLTProcessor.importStylesheet()`</span> function.

The resultant object depends on the [output method](https://www.w3.org/TR/xslt#output) of the stylesheet:

<table><thead><tr class="header"><th>Output method</th><th>Result type</th></tr></thead><tbody><tr class="odd"><td><code>html</code></td><td><a href="htmldocument"><code>HTMLDocument</code></a></td></tr><tr class="even"><td><code>xml</code></td><td><a href="xmldocument"><code>XMLDocument</code></a></td></tr><tr class="odd"><td><code>text</code></td><td><a href="xmldocument"><code>XMLDocument</code></a> with a single root element <code>&lt;transformiix:result&gt;</code> with the text as a child</td></tr></tbody></table>

 `[Throws] void `<span class="page-not-created">`XSLTProcessor.setParameter`</span>`(`[`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)` namespaceURI, `[`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)` localName, any value)`   
Sets a parameter in the XSLT stylesheet that was imported. (Sets the value of an `<xsl:param>`.) A null value for `namespaceURI` is treated the same as an empty string.

 `[Throws] any `<span class="page-not-created">`XSLTProcessor.getParameter`</span>`(`[`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)` namespaceURI, `[`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)` localName)`   
Gets the value of a parameter from the XSLT stylesheet. A null value for `namespaceURI` is treated the same as an empty string.

 `[Throws] void `<span class="page-not-created">`XSLTProcessor.removeParameter`</span>`(`[`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)` namespaceURI, `[`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)` localName)`   
Removes the parameter if it was previously set. This will make the `XSLTProcessor` use the default value for the parameter as specified in the stylesheet. A null value for `namespaceURI` is treated the same as an empty string.

 `void `<span class="page-not-created">`XSLTProcessor.clearParameters()`</span>   
Removes all set parameters from the `XSLTProcessor`. The `XSLTProcessor` will then use the defaults specified in the XSLT stylesheet.

 `void `<span class="page-not-created">`XSLTProcessor.reset()`</span>   
Removes all parameters and stylesheets from the `XSLTProcessor`.

Properties
----------

### Non-Web-exposed properties

The following properties are [`[ChromeOnly]`](https://developer.mozilla.org/en-US/docs/Mozilla/WebIDL_bindings#ChromeOnly) and not exposed to Web content:

 `[ChromeOnly] attribute unsigned long `<span class="page-not-created">`XSLTProcessor.flags`</span>   
Flags that tweak the behavior of the processor. Not reset by calling <span class="page-not-created">`XSLTProcessor.reset()`</span>. Default value: `0`

Possible values are:

<table><thead><tr class="header"><th>Name</th><th>Value</th><th>Effect</th></tr></thead><tbody><tr class="odd"><td>(None)</td><td><code>0</code></td><td>None</td></tr><tr class="even"><td><code>DISABLE_ALL_LOADS</code></td><td><code>1</code></td><td>Disable loading external documents (via e.g. <code>&lt;xsl:import&gt;</code> and <code>document()</code>)</td></tr></tbody></table>

Examples
--------

1.  [Basic example](https://developer.mozilla.org/en-US/docs/Web/XSLT/XSLT_JS_interface_in_Gecko/Basic_Example)
2.  [Advanced example](https://developer.mozilla.org/en-US/docs/Web/XSLT/XSLT_JS_interface_in_Gecko/Advanced_Example)
3.  [Additional example](https://developer.mozilla.org/en-US/docs/Web/XSLT/XSLT_JS_interface_in_Gecko/JavaScript_XSLT_Bindings)

Specifications
--------------

*Not part of any specification.* This is a proprietary interface that originated in Gecko.

Gecko IDL
---------

-   `XSLTProcessor.webidl`
-   `nsIXSLTProcessor.idl`

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

`XSLTProcessor`

1

12

Yes

No

≤12.1

3.1

1

18

Yes

≤12.1

2

1.0

`clearParameters`

1

12

Yes

No

≤12.1

3.1

1

18

Yes

≤12.1

2

1.0

`getParameter`

1

Chrome only supports string values.

12

Yes

No

≤12.1

Opera only supports string values.

3.1

1

Chrome only supports string values.

18

Chrome only supports string values.

Yes

≤12.1

Opera only supports string values.

2

1.0

Samsung Internet only supports string values.

`importStylesheet`

1

12

Yes

No

≤12.1

3.1

1

18

Yes

≤12.1

2

1.0

`removeParameter`

1

12

Yes

No

≤12.1

3.1

1

18

Yes

≤12.1

2

1.0

`reset`

1

12

Yes

No

≤12.1

3.1

1

18

Yes

≤12.1

2

1.0

`setParameter`

1

Chrome only supports string values.

12

Yes

No

≤12.1

Opera only supports string values.

3.1

1

Chrome only supports string values.

18

Chrome only supports string values.

Yes

≤12.1

Opera only supports string values.

2

1.0

Samsung Internet only supports string values.

`transformToDocument`

1

Chrome returns `null`if an error occurs.

12

Yes

Firefox throws an exception if an error occurs.

No

≤12.1

Opera returns `null`if an error occurs.

3.1

1

Chrome returns `null`if an error occurs.

18

Chrome returns `null`if an error occurs.

Yes

Firefox throws an exception if an error occurs.

≤12.1

Opera returns `null`if an error occurs.

2

1.0

Samsung Internet returns `null`if an error occurs.

`transformToFragment`

1

Chrome returns `null`if an error occurs.

12

Yes

Firefox throws an exception if an error occurs.

No

≤12.1

Opera returns `null`if an error occurs.

3.1

1

Chrome returns `null`if an error occurs.

18

Chrome returns `null`if an error occurs.

Yes

Firefox throws an exception if an error occurs.

≤12.1

Opera returns `null`if an error occurs.

2

1.0

Samsung Internet returns `null`if an error occurs.

See also
--------

-   [Using the Mozilla JavaScript interface to XSL Transformations](https://developer.mozilla.org/en-US/docs/Web/XSLT/Using_the_Mozilla_JavaScript_interface_to_XSL_Transformations)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XSLTProcessor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XSLTProcessor</a>
