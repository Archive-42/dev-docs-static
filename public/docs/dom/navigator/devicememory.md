# Navigator.deviceMemory

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `deviceMemory` read-only property of the [`Navigator`](../navigator) interface returns the approximate amount of device memory in gigabytes.

The reported value is imprecise to curtail fingerprinting. It’s approximated by rounding down to the nearest power of 2, then dividing that number by 1024. It is then clamped within lower and upper bounds to protect the privacy of owners of very low- or high-memory devices.

## Syntax

    memoryAmount = navigator.deviceMemory

### Value

A floating point number; one of `0.25`, `0.5`, `1`, `2`, `4`, `8`.

## Example

    const memory = navigator.deviceMemory
    console.log (`This device has at least ${memory}GiB of RAM.`)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/device-memory/#sec-device-memory-js-api">Device Memory 1<br />
<span class="small">The definition of 'deviceMemory' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`deviceMemory`

63

79

No

No

50

No

63

63

No

46

No

8.0

## See also

- [Device Memory API](../device_memory_api)
- [`Device-Memory`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Device-Memory) HTTP header

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/deviceMemory" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/deviceMemory</a>
