RTCIceServer.url
================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Draft**

This page is not complete.

*I'm experimenting with structure for pages documenting members of dictionaries. Please contact [sheppy](https://developer.mozilla.org/en-US/settings) with any feedback.*

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The **obsolete** [`RTCIceServer`](../rtciceserver) dictionary's `url` property specifies the URL of a single ICE server to be used while negotiating connections. It was removed from the specification in June 2013 but is still broadly used in older examples and books, so we include documentation here to help adapt old code to new browsers.

This property has been removed from the specification; while it's still supported by many browsers, it should no longer be used. You should instead use the newer [`urls`](urls) property, which allows you to optionally specify multiple URLs for the server. Try to update any existing code to use that property instead.

Syntax
------

    var iceServer = {
                      ...
                      url = iceServerUrl,
                      ...
                    };

    var serverUrl = iceServer.url;

    iceServer.url = iceServerUrl;

The value of this property is a [`DOMString`](../domstring) containing the full URL of a server to use during ICE negotiation.

Example
-------

This example creates a new [`RTCPeerConnection`](../rtcpeerconnection) which will use a [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) server at `stunserver.example.org` to negotiate connections.

    myPeerConnection = new RTCPeerConnection({
      iceServers: [
        {
          url: "stun:stunserver.example.org"
        }
      ]
    });

Unfortunately, the only way to tell ICE that the server has a backup domain name of `stunserver2.example.org` is to add a new entry to the `iceServers` array for it. The [`urls`](urls) property lets you include them both in one server, which is more readily maintainable.

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

See also
--------

-   [`RTCIceServer`](../rtciceserver)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceServer/url" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceServer/url</a>
