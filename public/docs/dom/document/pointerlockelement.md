# Document.pointerLockElement

The read-only `pointerLockElement` property of the [`Document`](../document) interface provides the element set as the target for mouse events while the pointer is locked. It is `null` if lock is pending, pointer is unlocked, or the target is in another document.

## Syntax

    document.pointerLockElement;

### Value

An [`Element`](../element) or `null`.

## Examples

Determine if a canvas element is currently pointer locked.

    if (document.pointerLockElement === canvasElement) {
      console.log('The pointer lock status is now locked');
      // Do something useful in response
    } else {
      console.log('The pointer lock status is now unlocked');
      // Do something useful in response
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/pointerlock/#extensions-to-the-documentorshadowroot-mixin">Pointer Lock<br />
<span class="small">The definition of 'pointerLockElement' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Extend the <code>Document</code> interface</td></tr></tbody></table>

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

`pointerLockElement`

37

12

50

No

24

10.1

37

37

50

24

No

3.0

## See also

- [`Document.exitPointerLock()`](exitpointerlock)
- [`Element.requestPointerLock()`](../element/requestpointerlock)
- [Pointer Lock](../pointer_lock_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerLockElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerLockElement</a>
