RTCPeerConnection.generateCertificate() static function
=======================================================

The static `RTCPeerConnection.generateCertificate()` function creates an X.509 certificate and corresponding private key, returning a promise that resolves with the new [`RTCCertificate`](../rtccertificate) once it's generated.

Syntax
------

    let certPromise = RTCPeerConnection.generateCertificate(keygenAlgorithm)

### Parameters

`keygenAlgorithm`  
A [Web Crypto API](../web_crypto_api) <span class="page-not-created">`AlgorithmIdentifier`</span> string or an <span class="page-not-created">`Algorithm`</span> -subclassed object specifying an algorithm to use when creating the certificate's key.

`RTCPeerConnection.generateCertificate()` is a static method, so it is always called on the `RTCPeerConnection` interface itself, not an instance thereof.

### Return value

A promise which resolves to a new [`RTCCertificate`](../rtccertificate) object containing a new key based on the specified options.

### Exceptions

`NotSupportedError`  
The normalized form of `keygenAlgorithm` specifies an algorithm or algorithm settings that the browser doesn't support, or which it does not allow for use with an [`RTCPeerConnection`](../rtcpeerconnection).

Other errors may occur; for example, if the specified `keygenAlgorithm` can't be successfully converted into an <span class="page-not-created">`RTCCertificateExpiration`</span> dictionary, the error that occurs during that conversion will be thrown.

Description
-----------

If a string is specified, it must be a [Web Crypto API](../web_crypto_api)-compatible algorithm name string. Alternatively, you can provide specific details for the algorithm's configuration by providing an object based on one of the Web Crypto API's <span class="page-not-created">`Algorithm`</span> class's subclasses.

### Standard configurations

All browsers are required to support the following two configurations. It's entirely possible that a browser's *default* settings may be different, but these are always supported.

#### RSASSA-PKCS1-v1\_5

    let stdRSACertificate = {
      name: "RSASSA-PKCS10-v1_5",
      modulusLength: 2048,
      publicExponent: new UInt8Array([1, 0, 1]),
      hash: "SHA-256"
    };

#### ECDSA

    let stdECDSACertificate = {
      name: "ECDSA",
      namedCurve: "P-256"
    };

### Certificate expiration time

By default the new certificate is configured with `expires` set to a [`DOMTimeStamp`](../domtimestamp) value of 2592000000, or 30 days. The expiration time cannot exceed 31536000000, or 365 days. It's also useful to note that browsers may further restrict the expiration time of certificates if they choose.

Examples
--------

### Specifying algorithm details

This example requests a new RSASSA-PKCS1-v1\_5 certificate using a SHA-256 hash and a modulus length of 2048.

    RTCPeerConnection.generateCertificate({
        name: 'RSASSA-PKCS1-v1_5',
        hash: 'SHA-256',
        modulusLength: 2048,
        publicExponent: new Uint8Array([1, 0, 1])
    }).then(function(cert) {
      var pc = new RTCPeerConnection({certificates: [cert]});
    });

### Specifying an algorithm by name

The example below specifies a string requesting an [ECDSA](https://en.wikipedia.org/wiki/Elliptic_Curve_Digital_Signature_Algorithm) certificate.

    RTCPeerConnection.generateCertificate("ECDSA");

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnection-generatecertificate">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.generateCertificate()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`generateCertificate`

48

79

22

No

43

Promise-based version.

37-43

12.1

48

48

44

43

Promise-based version.

37-43

12.2

6.0

See also
--------

-   [WebRTC API](../webrtc_api)
-   [Web Crypto API](../web_crypto_api)
-   [Web site security](https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps/Website_security)
-   [Web security](https://developer.mozilla.org/en-US/docs/Web/Security)
-   [Symmetric-key cryptography](https://developer.mozilla.org/en-US/docs/Glossary/Symmetric-key_cryptography)
-   `Window.crypto`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/generateCertificate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/generateCertificate</a>
