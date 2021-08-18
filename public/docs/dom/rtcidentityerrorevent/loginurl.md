# RTCIdentityErrorEvent.loginUrl

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The read-only property `RTCIdentityErrorEvent.loginUrl` is a [`DOMString`](../domstring) giving the URL where the user can complete the authentication. It can be `null` and is provided by the identity provider (idp).

Firefox implements the interface of this property under the following name: `RTCPeerConnectionIdentityErrorEvent.` It is likely that it will correct this name when it will unprefix [`RTCPeerConnection`](../rtcpeerconnection), once spec and implementation will have been stabilized.

## Syntax

    var loginUrl = event.loginUrl;
    event.loginUrl = "https://developer.mozilla.org/fakeURL";

## Example

    pc.onidpassertionerror = function( ev ) {
                               alert("The idp requested an authentication" +
                                     " to be performed at th3 URL '" +
                                     ev.url +
                                     "'.");
                             }

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

## See also

- `idpassertionerror`, `idpvalidationerror`
- [`RTCPeerConnection`](../rtcpeerconnection)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIdentityErrorEvent/loginUrl" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIdentityErrorEvent/loginUrl</a>
