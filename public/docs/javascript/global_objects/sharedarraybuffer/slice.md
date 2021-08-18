SharedArrayBuffer.prototype.slice()
===================================

The `SharedArrayBuffer.prototype.slice()` method returns a new [`SharedArrayBuffer`](../sharedarraybuffer) whose contents are a copy of this `SharedArrayBuffer`'s bytes from begin, inclusive, up to end, exclusive. If either begin or end is negative, it refers to an index from the end of the array, as opposed to from the beginning. This method has the same algorithm as [`Array.prototype.slice()`](../array/slice).

Syntax
------

    slice()
    slice(begin)
    slice(begin, end)

### Parameters

 `begin` <span class="badge inline optional">Optional</span>   
Zero-based index at which to begin extraction.

A negative index can be used, indicating an offset from the end of the sequence. `slice(-2)` extracts the last two elements in the sequence.

If `begin` is undefined, `slice` begins from index `0`.

 `end` <span class="badge inline optional">Optional</span>   
Zero-based index *before* which to end extraction. `slice` extracts up to but not including `end`.

For example, `slice(1,4)` extracts the second element through the fourth element (elements indexed 1, 2, and 3).

A negative index can be used, indicating an offset from the end of the sequence. `slice(2,-1)` extracts the third element through the second-to-last element in the sequence.

If `end` is omitted, `slice` extracts through the end of the sequence (`sab.byteLength`).

### Return value

A new [`SharedArrayBuffer`](../sharedarraybuffer) containing the extracted elements.

Examples
--------

### Using slice()

    var sab = new SharedArrayBuffer(1024);
    sab.slice();    // SharedArrayBuffer { byteLength: 1024 }
    sab.slice(2);   // SharedArrayBuffer { byteLength: 1022 }
    sab.slice(-2);  // SharedArrayBuffer { byteLength: 2 }
    sab.slice(0, 1); // SharedArrayBuffer { byteLength: 1 }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-sharedarraybuffer.prototype.slice">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-sharedarraybuffer.prototype.slice</span></a></td></tr></tbody></table>

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

`slice`

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

-   [`SharedArrayBuffer`](../sharedarraybuffer)
-   [`Array.prototype.slice()`](../array/slice)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer/slice" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer/slice</a>
