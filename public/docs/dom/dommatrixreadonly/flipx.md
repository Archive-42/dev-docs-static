# DOMMatrixReadOnly.flipX()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `flipX()` method of the [`DOMMatrixReadOnly`](../dommatrixreadonly) interface creates a new matrix being the result of the original matrix flipped about the x-axis.

## Syntax

    DOMMatrix.flipX()

### <span class="highlight-span">Return value</span>

Returns a [`DOMMatrix`](../dommatrix) containing a new matrix being the result of the original matrix flipped about the x-axis, which is equivalent to multiplying the matrix by `DOMMatrix(-1, 0, 0, 1, 0, 0)`. The original matrix is not modified.

## Examples

This SVG contains two paths in the shape of a triangle, both drawn to the same position. Note that the x co-ordinate of the viewBox attribute is negative, showing us content from both sides of the x-axis.

    <svg width="100" height="100" viewBox="-50 0 100 100">
      <path fill="red" d="M 0 50 L 50 0 L 50 100 Z" />
      <path id="flipped" fill="blue" d="M 0 50 L 50 0 L 50 100 Z" />
    </svg>

This JavaScript first creates an identity matrix, then uses the \`flipX()\` method to create a new matrix, which is then applied to the blue triangle, inverting it across the x-axis. The red triangle is left in place.

    const flipped = document.getElementById('flipped');
    const matrix = new DOMMatrixReadOnly();
    const flippedMatrix = matrix.flipX();
    flipped.setAttribute('transform', flippedMatrix.toString());

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAGQAAABkCAMAAABHPGVmAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAABCUExURQAA/xUA/5WS//9pZv+rqv/6+sTD//8AAP///w0A///s7P8/Ov/n5/85NP9raZ2Z/v9BPP9hXP9CPf+mpbuz99TT/1RTh28AAAIXSURBVGjetdjteoIwDIZhtukQxDnndv6nOkTA0ubjTUlyAvf1JL/a5nqKnmFouvdgo7/cm66JVfrv9jAioUr/0z6RQOVhzEiYMhkLEqSM90iREGU2XkiAshgJ4q6sRoo4Ky9jg7gq/bmlEUclNTLETUl2VSJOyqajRFyUzCgRByU3CGS3sr0Hg+xUig4a2aUQBo3sUCiDQaoV0uCQSoU2WKRKYQweqVA4Q0DMCmtIiFHhDRExKYIhIwZFMhQEVkRDQ0BFNlQEUhRDRwBFMwBEVVQDQRRluLQeiKgABoYICmKACKtABoowCmbACKmABo4QCmoYkEKBDQuSKbhhQpr0h2Q4tzFIolgMI7IqJsOKzIrNMCOTYjTsyKhYjQqkuVqNCqT7vYUj3efpeAtG3j7Hwx8/QpHJMCs2ZDasiglZDaNiQRJjVL5CkI1hasGRzLAoMFIYBgVFCANXQIQ0YAVDGANVIIQ1QAVBBANTAEQ0IEVHFANRVEQ1AEVDAENXFAQyVEVGQENTRAQ2FEVCDIasCIjJEBUeMRqSwiJmQ1A4pMLgFQapMliFRioNTiGRaoNRKGSHQSsEsssglRLZaVBKgew2CCVHHIxSyRAXo1C2iJORKxvEzcheFiniaGxbEsTV2LS8EGcjbVkRdyNpWZAA49UyIyHG2vJEgoxFmZAwY1YeSKDxVA5NrDEph2hjVG735u8UPcf+H3925F7/7hznAAAAAElFTkSuQmCC" class="internal" /></td><td></td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#dom-dommatrixreadonly-flipx">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'DOMMatrixReadOnly.flipX()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`flipX`

61

79

33

No

48

11

61

61

33

45

11

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMMatrixReadOnly/flipX" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMMatrixReadOnly/flipX</a>
