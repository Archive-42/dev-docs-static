# ResizeObserver.disconnect()

The `disconnect()` method of the [`ResizeObserver`](../resizeobserver) interface unobserves all observed [`Element`](../element) or [`SVGElement`](../svgelement) targets.

## Syntax

    resizeObserver.disconnect();

### Parameters

None.

### Return value

Void.

### Exceptions

None.

## Examples

    btn.addEventListener('click', () => {
      resizeObserver.disconnect();
    })

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/resize-observer/#dom-resizeobserver-disconnect">Resize Observer<br />
<span class="small">The definition of 'disconnect()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`disconnect`

64

79

69

No

51

13.1

64

64

79

47

13.4

9.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserver/disconnect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserver/disconnect</a>
