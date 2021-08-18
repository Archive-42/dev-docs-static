# RTCIceServer

The `RTCIceServer` dictionary defines how to connect to a single ICE server (such as a [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) or [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server). Objects of this type are provided in the [configuration](rtcconfiguration) of an [`RTCPeerConnection`](rtcpeerconnection), in the [`iceServers`](rtcconfiguration/iceservers) array.

## Properties

[`credential`](rtciceserver/credential) <span class="badge inline optional">Optional</span>  
The credential to use when logging into the server. This is only used if the `RTCIceServer` represents a TURN server.

[`credentialType`](rtciceserver/credentialtype) <span class="badge inline optional">Optional</span>  
If the `RTCIceServer` represents a TURN server, this attribute specifies what kind of `credential` is to be used when connecting. This must be one of the values defined by the [`RTCIceCredentialType`](rtcicecredentialtype) enum. The default is `password`.

[`urls`](rtciceserver/urls)  
This **required** property is either a single [`DOMString`](domstring) or an array of [`DOMString`](domstring)s, each specifying a URL which can be used to connect to the server.

[`username`](rtciceserver/username) <span class="badge inline optional">Optional</span>  
If the `RTCIceServer` is a TURN server, then this is the username to use during the authentication process.

Avoid specifying an unnecessarily large number of URLs in the `urls` property; the startup time for your connection will go up substantially. Every server in the list will be contacted and tried out before one is selected to be used for negotiation.

Older versions of the WebRTC specification included an `url` property instead of `urls`; this was changed in order to let you specify multiple addresses for each server in the list, as shown in the example below.

## Obsolete properties

_The following properties have been removed from the specification and should not be used._

[`url`](rtciceserver/url) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
This obsolete property is a string specifies a single ICE server's URL. **Do not use this property; use [`urls`](rtciceserver/urls) instead.** Because many older books and examples still use this, we include it to help developers update their code or make sense of older examples.

## Example

The configuration below establishes two ICE servers. The first one, `stun:stun.services.mozilla.com`, requires authentication, so the username and password are provided. The second server has two URLs: `stun:stun.example.com` and `stun:stun-1.example.com`.

    var configuration = { iceServers: [{
                              urls: "stun:stun.services.mozilla.com",
                              username: "louis@mozilla.com",
                              credential: "webrtcdemo"
                          }, {
                              urls: [
                                      "stun:stun.example.com",
                                      "stun:stun-1.example.com"
                              ]
                          }]
    };

    var pc = new RTCPeerConnection(configuration);

Once the configuration object has been created, it is passed into the [`RTCPeerConnection()`](rtcpeerconnection/rtcpeerconnection) constructor to use it as the configuration for the new peer connection.

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

`RTCIceServer`

Yes

≤79

22

No

?

?

No

Yes

24

?

?

Yes

`credential`

Yes

≤79

22

No

?

?

No

Yes

24

?

?

Yes

`credentialType`

Yes

≤79

47

No

?

?

No

Yes

47

?

?

Yes

`url`

Yes

≤79

22

No

?

?

No

Yes

24

?

?

Yes

`urls`

Yes

≤79

37

No

?

?

No

Yes

37

?

?

Yes

`username`

Yes

≤79

23

No

?

?

No

Yes

24

?

?

Yes

## See also

- [`RTCPeerConnection`](rtcpeerconnection)
- [`RTCConfiguration`](rtcconfiguration)
- [Lifetime of a WebRTC session](webrtc_api/session_lifetime)
- [WebRTC connectivity](webrtc_api/connectivity)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceServer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceServer</a>
