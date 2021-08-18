Tk
==

The `Tk` response header indicates the tracking status that applied to the corresponding request.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Tk: !  (under construction)
    Tk: ?  (dynamic)
    Tk: G  (gateway or multiple parties)
    Tk: N  (not tracking)
    Tk: T  (tracking)
    Tk: C  (tracking with consent)
    Tk: P  (potential consent)
    Tk: D  (disregarding DNT)
    Tk: U  (updated)

### Directives

!  
Under construction. The origin server is currently testing its communication of tracking status.

?  
Dynamic. The origin server needs more information to determine tracking status.

G  
Gateway or multiple parties. The server is acting as a gateway to an exchange involving multiple parties.

N  
Not tracking.

T  
Tracking.

C  
Tracking with consent. The origin server believes it has received prior consent for tracking this user, user agent, or device.

P  
Potential consent. The origin server does not know, in real-time, whether it has received prior consent for tracking this user, user agent, or device, but promises not to use or share any `DNT:1` data until such consent has been determined, and further promises to delete or permanently de-identify within 48 hours any `DNT:1` data received for which such consent has not been received.

D  
Disregarding DNT. The origin server is unable or unwilling to respect a tracking preference received from the requesting user agent.

U  
Updated. The request resulted in a potential change to the tracking status applicable to this user, user agent, or device.

Examples
--------

A `Tk` header for a resource that claims not to be tracking would look like:

    Tk: N

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/tracking-dnt/#Tk-header-defn">Tracking Preference Expression (DNT)<br />
<span class="small">The definition of 'Tk header field' in that specification.</span></a></td><td><span class="spec-Obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Tk`

?

?

?

?

?

?

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Tk`

?

?

?

?

?

?

See also
--------

-   [`DNT`](dnt) header
-   [`Navigator.doNotTrack`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/doNotTrack)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Tk$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Tk" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Tk</a>
