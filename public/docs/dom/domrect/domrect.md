# DOMRect.DOMRect()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `DOMRect()` constructor creates a new [`DOMRect`](../domrect) object.

## Syntax

    var myDOMRect = new DOMRect(x, y, width, height);

### Parameters

x  
The `x` coordinate of the `DOMRect`'s origin.

y  
The `y` coordinate of the `DOMRect`'s origin.

width  
The width of the `DOMRect`.

height  
The height of the `DOMRect`.

## Examples

To create a new `DOMRect`, you could run a line of code like so:

    myDOMRect = new DOMRect(0,0,100,100);
    // running 'myDOMRect' in the console would then return
    // DOMRect { x: 0, y: 0, width: 100, height: 100, top: 0, right: 100, bottom: 100, left: 0 }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#dom-domrect-domrect">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'DOMRect()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`DOMRect`

61

79

31

No

48

10.1

61

61

31

45

10.3

8.0

## See also

- [`DOMPoint`](../dompoint)
- [`DOMRect`](../domrect)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMRect/DOMRect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMRect/DOMRect</a>
