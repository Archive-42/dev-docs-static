RTCPeerConnection.getConfiguration()
====================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `RTCPeerConnection.getConfiguration()` method returns an [`RTCConfiguration`](../rtcconfiguration) object which indicates the current configuration of the [`RTCPeerConnection`](../rtcpeerconnection) on which the method is called.

The returned configuration is the last configuration applied via [`setConfiguration()`](setconfiguration), or if `setConfiguration()` hasn't been called, the configuration the `RTCPeerConnection` was constructed with. The configuration includes a list of the ICE servers used by the connection, information about transport policies, and identity information.

Syntax
------

    var configuration = RTCPeerConnection.getConfiguration();

### Parameters

This method takes no input parameters.

### Return value

An [`RTCConfiguration`](../rtcconfiguration) object describing the [`RTCPeerConnection`](../rtcpeerconnection)'s current configuration.

Example
-------

This example adds a new certificate to an active connection if it doesn't already have one in use.

    let configuration = myPeerConnection.getConfiguration();

    if ((configuration.certificates != undefined) && (!configuration.certificates.length)) {
       RTCPeerConnection.generateCertificate({
          name: 'RSASSA-PKCS1-v1_5',
          hash: 'SHA-256',
          modulusLength: 2048,
          publicExponent: new Uint8Array([1, 0, 1])
      }).then(function(cert) {
        configuration.certificates = [cert];
        myPeerConnection.setConfiguration(configuration);
      });
    }

This example fetches the current configuration of the [`RTCPeerConnection`](../rtcpeerconnection), then looks to see if it has any certificates set by examining whether or not (a) the configuration has a value for `certificates`, and (b) whether its length is zero.

If it's determined that there are no certificates in place, [`RTCPeerConnection.generateCertificate()`](generatecertificate) is called to create a new certificate; we provide a fulfillment handler which adds a new array containing the one newly-created certificate to the current configuration and passes it to <span class="page-not-created">`setConfiguration()`</span> to add the certificate to the connection.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnection-getconfiguration">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'getConfiguration()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getConfiguration`

70

15

22

No

43

Promise-based version.

37-43

11

70

70

44

43

Promise-based version.

37-43

11

6.0

See also
--------

-   [`RTCPeerConnection.setConfiguration()`](setconfiguration)
-   [`RTCConfiguration`](../rtcconfiguration)
-   [`RTCPeerConnection`](../rtcpeerconnection)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getConfiguration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getConfiguration</a>
