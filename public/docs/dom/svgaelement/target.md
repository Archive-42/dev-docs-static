SVGAElement.target
==================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `SVGAElement.target` read-only property of [`SVGAElement`](../svgaelement) returns an [`SVGAnimatedString`](../svganimatedstring) object that specifies the portion of a target window, frame, pane into which a document is to be opened when a link is activated.

This property is used when there are multiple possible targets for the ending resource, like when the parent document is a mlti-frame HTML or XHTML document.

Syntax
------

    myLink.target = 'value';

### Value

An [`SVGAnimatedString`](../svganimatedstring) indicating the ending resource target that opens the document when the link is activated.

Sample values can be found [here](https://www.w3.org/TR/2011/REC-SVG11-20110816/linking.html#AElementTargetAttribute)

Example
-------

The code is taken from the ["SVGAElement example code"](../svgaelement#example)

    ...
    var linkRef = document.querySelector('a');
    linkRef.target ='_blank';
    ...

Specifications
--------------

<table><tbody><tr class="odd"><td>Specification</td><td>Status</td><td>Comment</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/linking.html#InterfaceSVGAElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'target' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`target`

1

12

3

9

≤12.1

3

1

18

4

≤12.1

1

1.0

See also
--------

-   `target`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGAElement/target" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGAElement/target</a>
