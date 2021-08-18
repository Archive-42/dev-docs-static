RTCPeerConnection.getStreamById()
=================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `RTCPeerConnection.getStreamById()` method returns the [`MediaStream`](../mediastream) with the given id that is associated with local or remote end of the connection. If no stream matches, it returns `null`.

This property has been replaced with the [`RTCPeerConnection.getLocalStreams`](getsenders) and [`RTCPeerConnection.getRemoteStreams`](getreceivers) properties. If you have code that uses `stream`, you will need to update, since browsers have begun to remove support for `stream`.

Syntax
------

    var mediaStream = pc.getStream(id);

### Parameters

*id*  
Is a [`DOMString`](../domstring) corresponding to the stream to return.

Example
-------

    var stream = pc.getStreamById(myTrackId);
    if (stream) {
      console.log("Found stream: " + stream.id);
    }

Polyfill
--------

Running the following code before any other code will create `RTCPeerConnection.prototype.getStreamById()` if it's not natively available.

    // from: https://bugs.chromium.org/p/chromium/issues/detail?id=698163&desc=5#c10
    RTCPeerConnection.prototype.getStreamById = function(id) {
      try {
        var localStreams = this.getLocalStreams();
        var remoteStreams = this.getRemoteStreams();
        var i;
        for (i = 0; i < localStreams.length; i++) {
         if (localStreams[i].id == id)
           return localStreams[i];
        }
        for (i = 0; i < remoteStreams.length; i++) {
         if (remoteStreams[i].id == id)
           return remoteStreams[i];
        }
      } catch(e) {}
      return null;
    }

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

`getStreamById`

56-62

15-79

22-53

No

43

Promise-based version.

37-43

11-12

56-62

56-62

44

43

Promise-based version.

37-43

11-12.2

6.0-8.0

See also
--------

-   [WebRTC](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getStreamById" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getStreamById</a>
