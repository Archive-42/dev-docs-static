# RTCIdentityErrorEvent.idp

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The read-only property `RTCIdentityErrorEvent.idp` returns the [`DOMString`](../domstring) describing the [domain name](https://developer.mozilla.org/en-US/docs/Glossary/Domain_name) of the identity provider (idp) generating the error response event.

Firefox implements the interface of this property under the following name: `RTCPeerConnectionIdentityErrorEvent.` It is likely that it will correct this name when it will unprefix [`RTCPeerConnection`](../rtcpeerconnection), once spec and implementation will have been stabilized.

## Syntax

    var idp = event.idp;
    event.idp = "developer.mozilla.org";

## Example

    pc.onidpassertionerror = function( ev ) {
                               alert("The idp named '" +
                                     ev.idp +
                                     "' encountered an error " +
                                     "while generating an assertion.");
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

## See also

- `idpassertionerror`, `idpvalidationerror`
- [`RTCPeerConnection`](../rtcpeerconnection)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIdentityErrorEvent/idp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIdentityErrorEvent/idp</a>
