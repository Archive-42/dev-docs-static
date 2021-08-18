# RTCConfiguration.certificates

The [`RTCConfiguration`](../rtcconfiguration) dictionary's optional `certificates` property is an array of [`RTCCertificate`](../rtccertificate) objects providing the security certificates available for use when authenticating duing the connection process.

## Syntax

    let rtcConfiguration = {
      certificates: certificateList
    };

    let rtcConfiguration.certificates = [ cert1... ];
    let certificates = rtcConfiguration.certificates;

### Value

An array of [`RTCCertificate`](../rtccertificate) objects, each specifying one security certificate available for use when connecting to a remote peer. If this property isn't specified, the browser will automatically generate and use a certificate to secure the connection.

See [Using certificates](#using_certificates) below for more information on why you might want to—or not to—explicitly provide certificates.

## Description

If this property isn't included in the configuration, a set of certificates is automatically generated for each instance of [`RTCPeerConnection`](../rtcpeerconnection). Although a given [DTLS](https://developer.mozilla.org/en-US/docs/Glossary/DTLS) connection only uses a single certificate, providing multiple options in the `certificates` list may improve the odds of establishing a connection by increasing the chances a mutually-compatible encryption algorithm and key size may be found.

The method by which a browser decides which certificate to use is implementation-dependent. Some browsers may choose the first listed certificate and ignore the rest of the list; others may take a different approach.

### Using certificates

When you wish to provide your own certificates for use by an [`RTCPeerConnection`](../rtcpeerconnection) instead of having the `RTCPeerConnection` generate them automatically, you do so by calling the static [`RTCPeerConnection.generateCertificate()`](../rtcpeerconnection/generatecertificate) function.

The `certificates` property's value cannot be changed once it's first specified. If it's included in the configuration passed into a call to a connection's [`setConfiguration()`](../rtcpeerconnection/setconfiguration), it is ignored.

This attribute supports providing multiple certificates because even though a given DTLS connection uses only one certificate, providing multiple certificates allows support for multiple encryption algorithms. The implementation of `RTCPeerConnection` will choose which certificate to use based on the algorithms it and the remote peer support, as determined during DTLS handshake.

If you don't provide certificates, new ones are generated automatically. One obvious benefit to providing your own is identity key continuity—if you use the same certificate for subsequent calls, the remote peer can tell you're the same caller. This also avoids the cost of generating new keys.

**&lt;&lt;&lt;--- add link to information about identity ---&gt;&gt;&gt;**

## Examples

This example uses [`RTCPeerConnection.generateCertificate()`](../rtcpeerconnection/generatecertificate) to create a certificate, then uses it to open a new [`RTCPeerConnection`](../rtcpeerconnection).

    RTCPeerConnection.generateCertificate({
        name: 'RSASSA-PKCS1-v1_5',
        hash: 'SHA-256',
        modulusLength: 2048,
        publicExponent: new Uint8Array([1, 0, 1])
    }).then(function(cert) {
      var pc = new RTCPeerConnection({certificates: [cert]});
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcconfiguration-certificates">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCConfiguration.certificates' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`certificates`

23

≤79

?

No

Yes

?

≤37

57

?

Yes

?

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCConfiguration/certificates" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCConfiguration/certificates</a>
