SharedArrayBuffer() constructor
===============================

**Note:** `SharedArrayBuffer` was disabled by default in all major browsers on 5 January, 2018 in response to [Spectre](https://meltdownattack.com/). Chrome [re-enabled it in v67](https://bugs.chromium.org/p/chromium/issues/detail?id=821270) on platforms where its site-isolation feature is enabled to protect against Spectre-style vulnerabilities.

The `SharedArrayBuffer()` is used to create a [`SharedArrayBuffer`](../sharedarraybuffer) object representing a generic, fixed-length raw binary data buffer, similar to the [`ArrayBuffer`](../arraybuffer) object.

Syntax
------

    new SharedArrayBuffer()
    new SharedArrayBuffer(length)

### Parameters

 `length` <span class="badge inline optional">Optional</span>   
The size, in bytes, of the array buffer to create.

### Return value

A new `SharedArrayBuffer` object of the specified size. Its contents are initialized to 0.

Examples
--------

### Always use the new operator to create a SharedArrayBuffer

`SharedArrayBuffer` constructors are required to be constructed with a [`new`](../../operators/new) operator. Calling a `SharedArrayBuffer` constructor as a function without `new` will throw a [`TypeError`](../typeerror).

    var sab = SharedArrayBuffer(1024);
    // TypeError: calling a builtin SharedArrayBuffer constructor
    // without new is forbidden

    var sab = new SharedArrayBuffer(1024);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-sharedarraybuffer-constructor">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-sharedarraybuffer-constructor</span></a></td></tr></tbody></table>

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

`SharedArrayBuffer`

68

60-63

Chrome disabled SharedArrayBuffer on January 5, 2018 to help reduce the efficacy of [speculative side-channel attacks](https://www.chromium.org/Home/chromium-security/ssca). This was a temporary removal while mitigations were put in place.

79

16-17

Support was removed to mitigate [speculative execution side-channel attacks (Windows blog)](https://blogs.windows.com/msedgedev/2018/01/03/speculative-execution-mitigations-microsoft-edge-internet-explorer).

79

57

Support was disabled by default to mitigate [speculative execution side-channel attacks (Mozilla Security Blog)](https://blog.mozilla.org/security/2018/01/03/mitigations-landing-new-class-timing-attack/).

55-57

46-55

No

No

10.1-11

60-63

Chrome disabled SharedArrayBuffer on January 5, 2018 to help reduce the efficacy of [speculative side-channel attacks](https://www.chromium.org/Home/chromium-security/ssca). This is intended as a temporary measure until other mitigations are in place.

89

`SharedArrayBuffer` is gated behind COOP/COEP. For more detail, read [Making your website "cross-origin isolated" using COOP and COEP](https://web.dev/coop-coep/).

60-63

Chrome disabled SharedArrayBuffer on January 5, 2018 to help reduce the efficacy of [speculative side-channel attacks](https://www.chromium.org/Home/chromium-security/ssca). This is intended as a temporary measure until other mitigations are in place.

79

57

Support was disabled by default to mitigate [speculative execution side-channel attacks (Mozilla Security Blog)](https://blog.mozilla.org/security/2018/01/03/mitigations-landing-new-class-timing-attack/).

55-57

46-55

No

10.3-11

No

Chrome disabled SharedArrayBuffer on January 5, 2018 to help reduce the efficacy of [speculative side-channel attacks](https://www.chromium.org/Home/chromium-security/ssca). This is intended as a temporary measure until other mitigations are in place.

See also
--------

-   [`Atomics`](../atomics)
-   [`ArrayBuffer`](../arraybuffer)
-   [JavaScript typed arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Typed_arrays)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer/SharedArrayBuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer/SharedArrayBuffer</a>
