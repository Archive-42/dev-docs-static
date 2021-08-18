RTCPeerConnection.getDefaultIceServers()
========================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `getDefaultIceServers()` method of the [`RTCPeerConnection`](../rtcpeerconnection) interface returns an array of objects based on the [`RTCIceServer`](../rtciceserver) dictionary, which indicates what, if any, ICE servers the browser will use by default if none are provided to the [`RTCPeerConnection`](../rtcpeerconnection) in its [`RTCConfiguration`](../rtcconfiguration). However, browsers are **not** required to provide any default ICE servers at all.

Syntax
------

     var defaultIceServers = RTCPeerConnection.getDefaultIceServers();

### Return value

An array of ICE servers, specified as objects based on [`RTCIceServer`](../rtciceserver), which the browser will use if none are specified in the configuration of the [`RTCPeerConnection`](../rtcpeerconnection). If there are no defaults provided by the browser, the returned array is empty; this property's value is never `null`.

Example
-------

    var pc = new RTCPeerConnection();
    var iceServers = pc.getDefaultIceServers();

    if (iceServers.length === 0) {
      // Deal with the lack of default ICE servers, possibly by using our own defaults
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-extensions/#dom-rtcpeerconnection-getdefaulticeservers">WebRTC Extensions</a></td><td></td><td></td></tr></tbody></table>

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

`getDefaultIceServers`

No

No

?

No

?

No

No

No

?

?

No

No

See also
--------

-   [WebRTC](../webrtc_api)
-   [`RTCConfiguration`](../rtcconfiguration)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getDefaultIceServers" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getDefaultIceServers</a>
