# Document.exitPointerLock()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `exitPointerLock()` method asynchronously releases a pointer lock previously requested through [`Element.requestPointerLock`](../element/requestpointerlock).

To track the success or failure of the request, it is necessary to listen for the `pointerlockchange` and `pointerlockerror` events.

## Syntax

    document.exitPointerLock();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/pointerlock/#extensions-to-the-document-interface">Pointer Lock<br />
<span class="small">The definition of 'Document' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Extend the <code>Document</code> interface</td></tr></tbody></table>

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

`exitPointerLock`

37

22

13

50

Yes

No

24

15

10.1

37

≤37

37

25

50

Yes

24

14

10.3

3.0

1.5

## See also

- [`Document.pointerLockElement`](pointerlockelement)
- [`Element.requestPointerLock()`](../element/requestpointerlock)
- [Pointer Lock](../pointer_lock_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/exitPointerLock" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/exitPointerLock</a>
