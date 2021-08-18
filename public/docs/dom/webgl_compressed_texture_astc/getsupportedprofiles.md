WEBGL\_compressed\_texture\_astc.getSupportedProfiles()
=======================================================

The `WEBGL_compressed_texture_astc.getSupportedProfiles()` method returns an array of strings containing the names of the ASTC profiles supported by the implementation.

Syntax
------

    sequence<DOMString> ext.getSupportedProfiles();

### Return value

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`DOMString`](../domstring) elements indicating which ASTC profiles are supported by the implementation. Currently, this can be:

-   "ldr": Low Dynamic Range.
-   "hdr": High Dynamic Range.

Dynamic range refers to ratio between the brightest and darkest parts of the scene. Low dynamic ranges are for example JPEG format images which won't exceed 255:1, or CRT monitors which won't exceed 100:1. An HDR image stores pixel values that span the whole tonal range of real-world scenes (100,000:1).

Examples
--------

    var ext = gl.getExtension('WEBGL_compressed_texture_astc');
    ext.getSupportedProfiles(); // ["ldr"]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/WEBGL_compressed_texture_astc/">WEBGL_compressed_texture_astc<br />
<span class="small">The definition of 'WEBGL_compressed_texture_astc' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getSupportedProfiles`

47

79

53

No

?

No

47

47

53

?

No

5.0

See also
--------

-   [`WEBGL_compressed_texture_astc`](../webgl_compressed_texture_astc)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_compressed_texture_astc/getSupportedProfiles" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_compressed_texture_astc/getSupportedProfiles</a>
