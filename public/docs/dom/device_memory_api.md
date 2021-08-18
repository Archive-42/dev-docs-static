# Device Memory API

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The capabilities of a client device largely depend on the amount of available RAM. Traditionally, developers had to use heuristics and either benchmark a device or infer device capabilities based on other factors like the device manufacturer or User Agent strings.

## Determining device memory

There are two ways to determine the approximate amount of RAM a device has: use the Device Memory JavaScript API or accept Client Hints.

### JavaScript API

You may query the approximate amount of RAM a device has by retrieving [`Navigator.deviceMemory`](navigator/devicememory)

    var RAM = navigator.deviceMemory;

### Client Hints

You may also use the [Client Hints](https://developer.mozilla.org/en-US/docs/Glossary/Client_hints) HTTP Header with the `Device-Memory` directive to retrieve the same approximate RAM capacity.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/device-memory/">Device Memory 1</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Device_Memory_API`

61

≤79

?

?

48

No

61

61

?

?

No

8.0

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

`Device_Memory_API`

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

BCD tables only load in the browser

### Client Hints extension

BCD tables only load in the browser

## See also

- [`Navigator.deviceMemory`](navigator/devicememory)
- [`Device-Memory`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Device-Memory) header

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Device_Memory_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Device_Memory_API</a>
