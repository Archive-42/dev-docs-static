RTCIdentityErrorEvent
=====================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `RTCIdentityErrorEvent` interface represents an error associated with the identity provider (idP). This is usually for an [`RTCPeerConnection`](rtcpeerconnection). Two events are sent with this type: `idpassertionerror` and `idpvalidationerror`.

Firefox implements this interface under the following name: `RTCPeerConnectionIdentityErrorEvent.` It is likely that it will correct this name when it will unprefix [`RTCPeerConnection`](rtcpeerconnection), once spec and implementation will have been stabilized.

Properties
----------

*A [`RTCIdentityErrorEvent`](rtcidentityerrorevent) being an [`Event`](event), this event also implements these properties*.

 [`RTCIdentityErrorEvent.idp`](rtcidentityerrorevent/idp) <span class="badge inline readonly">Read only </span>   
Is a [`DOMString`](domstring) describing the [domain name](https://developer.mozilla.org/en-US/docs/Glossary/Domain_name) of the identity provider (idp) generating the error response.

 [`RTCIdentityErrorEvent.loginUrl`](rtcidentityerrorevent/loginurl) <span class="badge inline readonly">Read only </span>   
Is a [`DOMString`](domstring) giving the URL where the user can complete the authentication. It can be `null` and is provided by the identity provider (idp).

 [`RTCIdentityErrorEvent.protocol`](rtcidentityerrorevent/protocol) <span class="badge inline readonly">Read only </span>   
Is a [`DOMString`](domstring) describing the Idp protocol in use.

Methods
-------

*A [`RTCIdentityErrorEvent`](rtcidentityerrorevent) being an [`Event`](event), this event also implements these properties. There is no specific [`RTCIdentityErrorEvent`](rtcidentityerrorevent) method.*

Examples
--------

    pc.onidpassertionerror = function( ev ) {
                               alert("The idp named '" +
                                     ev.idp +
                                     "' encountered an error " +
                                     "while generating an assertion.");
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

`RTCIdentityErrorEvent`

No

No

Yes

No

Yes

?

No

No

?

?

No

No

`idp`

No

No

?

No

Yes

?

No

No

?

?

No

No

`loginUrl`

No

No

?

No

Yes

?

No

No

?

?

No

No

`protocol`

No

No

?

No

Yes

?

No

No

?

?

No

No

See also
--------

-   [WebRTC](webrtc_api)
-   Its usual target: [`RTCPeerConnection`](rtcpeerconnection).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIdentityErrorEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIdentityErrorEvent</a>
