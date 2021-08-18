Index
=====

**Found 122 pages:**

\#

Page

Tags and summary

1

[HTTP headers](../headers)

**HTTP, HTTP Header, Networking, Overview, Reference**

HTTP headers allow the client and the server to pass additional information with the request or the response. An HTTP header consists of its case-insensitive name followed by a colon '`:`', then by its value (without line breaks). Leading white space before the value is ignored.

2

[Accept](accept)

**HTTP, HTTP Header, Reference, Request header**

The `Accept` request HTTP header advertises which content types, expressed as [MIME types](../basics_of_http/mime_types), the client is able to understand. Using [content negotiation](../content_negotiation), the server then selects one of the proposals, uses it and informs the client of its choice with the [`Content-Type`](content-type) response header. Browsers set adequate values for this header depending on the context where the request is done: when fetching a CSS stylesheet a different value is set for the request than when fetching an image, video or a script.

3

[Accept-Charset](accept-charset)

**Content Negotiation, HTTP, HTTP Header, Reference, Request header**

The `Accept-Charset` request HTTP header advertises which character set the client is able to understand. Using [content negotiation](../content_negotiation), the server then selects one of the proposals, uses it and informs the client of its choice within the [`Content-Type`](content-type) response header. Browsers usually don't set this header as the default value for each content type is usually correct and transmitting it would allow easier fingerprinting.

4

[Accept-Encoding](accept-encoding)

**Content Negotiation, HTTP, HTTP Header, Reference, Request header**

The `Accept-Encoding` request HTTP header advertises which content encoding, usually a compression algorithm, the client is able to understand. Using [content negotiation](../content_negotiation), the server selects one of the proposals, uses it and informs the client of its choice with the [`Content-Encoding`](content-encoding) response header.

5

[Accept-Language](accept-language)

**Content Negotiation, HTTP, HTTP Header, Reference, Request header**

The `Accept-Language` request HTTP header advertises which languages the client is able to understand, and which locale variant is preferred. (By languages, we mean natural languages, such as English, and not programming languages.) Using [content negotiation](../content_negotiation), the server then selects one of the proposals, uses it and informs the client of its choice with the [`Content-Language`](content-language) response header. Browsers set adequate values for this header according to their user interface language and even if a user can change it, this happens rarely (and is frowned upon as it leads to fingerprinting).

6

[Accept-Ranges](accept-ranges)

**HTTP, HTTP Header, Range Requests, Reference, Response Header**

The `Accept-Ranges` response HTTP header is a marker used by the server to advertise its support of partial requests. The value of this field indicates the unit that can be used to define a range.

7

[Access-Control-Allow-Credentials](access-control-allow-credentials)

**CORS, HTTP, Reference, header**

The `Access-Control-Allow-Credentials` response header tells browsers whether to expose the response to frontend JavaScript code when the request's credentials mode ([`Request.credentials`](https://developer.mozilla.org/en-US/docs/Web/API/Request/credentials)) is "`include`".

8

[Access-Control-Allow-Headers](access-control-allow-headers)

**CORS, HTTP, Reference, header**

The `Access-Control-Allow-Headers` response header is used in response to a [preflight request](https://developer.mozilla.org/en-US/docs/Glossary/preflight_request) which includes the [`Access-Control-Request-Headers`](access-control-request-headers) to indicate which HTTP headers can be used during the actual request.

9

[Access-Control-Allow-Methods](access-control-allow-methods)

**CORS, HTTP, Reference, header**

The `Access-Control-Allow-Methods` response header specifies the method or methods allowed when accessing the resource in response to a [preflight request](https://developer.mozilla.org/en-US/docs/Glossary/preflight_request).

10

[Access-Control-Allow-Origin](access-control-allow-origin)

**Access Control, Access-Control-Allow-Origin, CORS, Dealing with CORS, HTTP, HTTP Header, How to Fix CORS, Reference, Security, cross-origin issue, header, origin**

The `Access-Control-Allow-Origin` response header indicates whether the response can be shared with requesting code from the given [origin](https://developer.mozilla.org/en-US/docs/Glossary/origin).

11

[Access-Control-Expose-Headers](access-control-expose-headers)

**CORS, HTTP, Reference, header**

The `Access-Control-Expose-Headers` response header indicates which headers can be exposed as part of the response by listing their names.

12

[Access-Control-Max-Age](access-control-max-age)

**CORS, HTTP, Reference, header**

The `Access-Control-Max-Age` response header indicates how long the results of a [preflight request](https://developer.mozilla.org/en-US/docs/Glossary/preflight_request) (that is the information contained in the [`Access-Control-Allow-Methods`](access-control-allow-methods) and [`Access-Control-Allow-Headers`](access-control-allow-headers) headers) can be cached.

13

[Access-Control-Request-Headers](access-control-request-headers)

**CORS, HTTP, Reference, header**

The `Access-Control-Request-Headers` request header is used when issuing a [preflight request](https://developer.mozilla.org/en-US/docs/Glossary/preflight_request) to let the server know which [HTTP headers](../headers) will be used when the actual request is made.

14

[Access-Control-Request-Method](access-control-request-method)

**CORS, HTTP, Reference, header**

The `Access-Control-Request-Method` request header is used when issuing a [preflight request](https://developer.mozilla.org/en-US/docs/Glossary/preflight_request) to let the server know which [HTTP method](../methods) will be used when the actual request is made. This header is necessary as the preflight request is always an [`OPTIONS`](../methods/options) and doesn't use the same method as the actual request.

15

[Age](age)

**Caching, HTTP, Response, header**

The `Age` header contains the time in seconds the object has been in a proxy cache.

16

[Allow](allow)

**Entity header, HTTP, HTTP Header, Reference, header**

The `Allow` header lists the set of methods support by a resource.

17

[Alt-Svc](alt-svc)

**Draft, HTTP, HTTP Header, NeedsCompatTable, NeedsContent, NeedsExample, Reference**

The `Alt-Svc` header is used to list alternate ways to reach this website.

18

[Authorization](authorization)

**HTTP, HTTP Header, Reference, Request header, header**

The HTTP `Authorization` request header contains the credentials to authenticate a user agent with a server, usually after the server has responded with a [`401`](../status/401) `Unauthorized` status and the [`WWW-Authenticate`](www-authenticate) header.

19

[Cache-Control](cache-control)

**General Header, HTTP, HTTP Header, Reference**

The `Cache-Control` general-header field is used to specify directives for caching mechanisms in both requests and responses. Caching directives are unidirectional, meaning that a given directive in a request is not implying that the same directive is to be given in the response.

20

[Clear-Site-Data](clear-site-data)

**HTTP, HTTP Header, Reference, header**

The `Clear-Site-Data` header clears browsing data (cookies, storage, cache) associated with the requesting website. It allows web developers to have more control over the data stored locally by a browser for their origins.

21

[Connection](connection)

**HTTP, Headers, Reference, Web**

The `Connection` general header controls whether or not the network connection stays open after the current transaction finishes. If the value sent is `keep-alive`, the connection is persistent and not closed, allowing for subsequent requests to the same server to be done.

22

[Content-Disposition](content-disposition)

**HTTP, Reference, header**

In a `multipart/form-data` body, the HTTP `Content-Disposition` general header is a header that can be used on the subpart of a multipart body to give information about the field it applies to. The subpart is delimited by the *boundary* defined in the [`Content-Type`](content-type) header. Used on the body itself, `Content-Disposition` has no effect.

23

[Content-Encoding](content-encoding)

**HTTP, Headers, Reference**

The `Content-Encoding` entity header is used to compress the media-type. When present, its value indicates which encodings were applied to the entity-body. It lets the client know how to decode in order to obtain the media-type referenced by the `Content-Type` header.

24

[Content-Language](content-language)

**HTTP, Headers, Reference**

The `Content-Language` [entity header](https://developer.mozilla.org/en-US/docs/Glossary/entity_header) is used to describe the language(s) intended for the audience, so that it allows a user to differentiate according to the users' own preferred language.

25

[Content-Length](content-length)

**HTTP, Headers, Reference**

The `Content-Length` entity header indicates the size of the entity-body, in bytes, sent to the recipient.

26

[Content-Location](content-location)

**HTTP, Reference, header**

The `Content-Location` header indicates an alternate location for the returned data. The principal use is to indicate the URL of a resource transmitted as the result of [content negotiation](../content_negotiation).

27

[Content-Range](content-range)

**HTTP, HTTP Header, Reference, Response Header, header**

The `Content-Range` response HTTP header indicates where in a full body message a partial message belongs.

28

[Content-Security-Policy](content-security-policy)

**CSP, HTTP, Reference, Security, header**

The HTTP `Content-Security-Policy` response header allows web site administrators to control resources the user agent is allowed to load for a given page. With a few exceptions, policies mostly involve specifying server origins and script endpoints. This helps guard against cross-site scripting attacks ([XSS](https://developer.mozilla.org/en-US/docs/Glossary/XSS)).

29

[CSP: base-uri](content-security-policy/base-uri)

**CSP, Directive, Document directive, HTTP, Security**

The HTTP [`Content-Security-Policy`](content-security-policy) `base-uri` directive restricts the URLs which can be used in a document's [`<base>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/base) element. If this value is absent, then any URI is allowed. If this directive is absent, the user agent will use the value in the [`<base>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/base) element.

30

[CSP: block-all-mixed-content](content-security-policy/block-all-mixed-content)

**CSP, Directive, HTTP, Mixed Content, Reference, Security**

The HTTP [`Content-Security-Policy`](content-security-policy) (CSP) `block-all-mixed-content` directive prevents loading any assets using HTTP when the page is loaded using HTTPS.

31

[CSP: child-src](content-security-policy/child-src)

**CSP, Directive, HTTP, Reference, Security**

The deprecated HTTP [`Content-Security-Policy`](content-security-policy) (CSP) `child-src` directive defines the valid sources for [web workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API) and nested browsing contexts loaded using elements such as [`<frame>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frame) and [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe). For workers, non-compliant requests are treated as fatal network errors by the user agent.

32

[CSP: connect-src](content-security-policy/connect-src)

**CSP, Directive, HTTP, Reference, Security**

The HTTP [`Content-Security-Policy`](content-security-policy) (CSP) `connect``-src` directive restricts the URLs which can be loaded using script interfaces. The APIs that are restricted are:

33

[CSP: default-src](content-security-policy/default-src)

**CSP, Directive, HTTP, Reference, Security**

The HTTP [`Content-Security-Policy`](content-security-policy) (CSP) `default``-src` directive serves as a fallback for the other CSP [fetch directives](https://developer.mozilla.org/en-US/docs/Glossary/fetch_directive). For each of the following directives that are absent, the user agent will look for the `default-src` directive and will use this value for it:

34

[CSP: font-src](content-security-policy/font-src)

**CSP, Directive, HTTP, Reference, Security**

The HTTP [`Content-Security-Policy`](content-security-policy) (CSP) `font``-src` directive specifies valid sources for fonts loaded using [`@font-face`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face).

35

[CSP: form-action](content-security-policy/form-action)

**CSP, Directive, HTTP, Security**

The HTTP [`Content-Security-Policy`](content-security-policy) (CSP) `form``-action` directive restricts the URLs which can be used as the target of a form submissions from a given context.

36

[CSP: frame-ancestors](content-security-policy/frame-ancestors)

**CSP, Directive, HTTP, Security**

The HTTP [`Content-Security-Policy`](content-security-policy) (CSP) `frame-ancestors` directive specifies valid parents that may embed a page using [`<frame>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frame), [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe), [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object), [`<embed>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed), or [`<applet>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/applet).

37

[CSP: frame-src](content-security-policy/frame-src)

**CSP, Directive, HTTP, Reference, Security**

The HTTP [`Content-Security-Policy`](content-security-policy) (CSP) `frame-src` directive specifies valid sources for nested browsing contexts loading using elements such as [`<frame>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frame) and [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe).

38

[CSP: img-src](content-security-policy/img-src)

**CSP, Directive, HTTP, Reference, Security**

The HTTP [`Content-Security-Policy`](content-security-policy) `img``-src` directive specifies valid sources of images and favicons.

39

[CSP: manifest-src](content-security-policy/manifest-src)

**CSP, Directive, HTTP, Reference, Security**

The HTTP [`Content-Security-Policy`](content-security-policy)`:` `manifest``-src` directive specifies which [manifest](https://developer.mozilla.org/en-US/docs/Web/Manifest) can be applied to the resource.

40

[CSP: media-src](content-security-policy/media-src)

**CSP, Directive, HTTP, Reference, Security**

The HTTP [`Content-Security-Policy`](content-security-policy) (CSP) `media``-src` directive specifies valid sources for loading media using the [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) and [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) elements.

41

[CSP: object-src](content-security-policy/object-src)

**CSP, Directive, HTTP, Reference, Security**

The HTTP [`Content-Security-Policy`](content-security-policy) `object``-src` directive specifies valid sources for the [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object), [`<embed>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed), and [`<applet>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/applet) elements.

42

[CSP: plugin-types](content-security-policy/plugin-types)

**CSP, Directive, Flash, HTTP, Java, Plugins, Security**

The HTTP [`Content-Security-Policy`](content-security-policy) (CSP) `plugin-types` directive restricts the set of plugins that can be embedded into a document by limiting the types of resources which can be loaded.

43

[CSP: referrer](content-security-policy/referrer)

**CSP, Directive, HTTP, Reference, Security**

The HTTP [`Content-Security-Policy`](content-security-policy) (CSP) `referrer` directive used to specify information in the [`Referer`](referer) header (with a single `r` as this was a typo in the original spec) for links away from a page. This API is deprecated and removed from browsers.

44

[CSP: report-uri](content-security-policy/report-uri)

**CSP, Directive, HTTP, Reference, Security**

The deprecated HTTP [`Content-Security-Policy`](content-security-policy) (CSP) `report-uri` directive instructs the user agent to report attempts to violate the Content Security Policy. These violation reports consist of JSON documents sent via an HTTP POST request to the specified URI.

45

[CSP: require-sri-for](content-security-policy/require-sri-for)

**CSP, Directive, HTTP, Reference, Security**

The HTTP [`Content-Security-Policy`](content-security-policy) `require-sri-for` directive instructs the client to require the use of [Subresource Integrity](https://developer.mozilla.org/en-US/docs/Web/Security/Subresource_Integrity) for scripts or styles on the page.

46

[CSP: sandbox](content-security-policy/sandbox)

**CSP, Directive, HTTP, Security**

The HTTP [`Content-Security-Policy`](content-security-policy) (CSP) `sandbox` directive enables a sandbox for the requested resource similar to the [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) `sandbox` attribute. It applies restrictions to a page's actions including preventing popups, preventing the execution of plugins and scripts, and enforcing a same-origin policy.

47

[CSP: script-src](content-security-policy/script-src)

**CSP, Directive, HTTP, Reference, Security**

The HTTP [`Content-Security-Policy`](content-security-policy) (CSP) `script-src` directive specifies valid sources for JavaScript. This includes not only URLs loaded directly into [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) elements, but also things like inline script event handlers (`onclick`) and [XSLT stylesheets](https://developer.mozilla.org/en-US/docs/Web/XSLT) which can trigger script execution.

48

[CSP: style-src](content-security-policy/style-src)

**CSP, Directive, HTTP, Reference, Security**

The HTTP [`Content-Security-Policy`](content-security-policy) (CSP) `style``-src` directive specifies valid sources for stylesheets.

49

[CSP: upgrade-insecure-requests](content-security-policy/upgrade-insecure-requests)

**CSP, Directive, HTTP, Reference, Security**

The HTTP [`Content-Security-Policy`](content-security-policy) (CSP) `upgrade-insecure-requests` directive instructs user agents to treat all of a site's insecure URLs (those served over HTTP) as though they have been replaced with secure URLs (those served over HTTPS). This directive is intended for web sites with large numbers of insecure legacy URLs that need to be rewritten.

50

[CSP: worker-src](content-security-policy/worker-src)

**CSP, Directive, HTTP, Reference, Security**

The HTTP [`Content-Security-Policy`](content-security-policy) (CSP) `worker-src` directive specifies valid sources for [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker), [`SharedWorker`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker), or [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker) scripts.

51

[report-to](content-security-policy/report-to)

**CSP, HTTP, report-to**

The `Report-To` HTTP response header field instructs the user agent to store reporting endpoints for an origin.

52

[Content-Security-Policy-Report-Only](content-security-policy-report-only)

**CSP, HTTP, HTTPS, Reference, Security, header**

The HTTP `Content-Security-Policy-Report-Only` response header allows web developers to experiment with policies by monitoring (but not enforcing) their effects. These violation reports consist of [JSON](https://developer.mozilla.org/en-US/docs/Glossary/JSON) documents sent via an HTTP `POST` request to the specified URI.

53

[Content-Type](content-type)

**Content-Type, HTTP, Reference, Request header, header**

The `Content-Type` entity header is used to indicate the [media type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type) of the resource.

54

[Cookie](cookie)

**Cookies, HTTP, Reference, header, request**

The `Cookie` HTTP request header contains stored [HTTP cookies](../cookies) previously sent by the server with the [`Set-Cookie`](set-cookie) header.

55

[Cookie2](cookie2)

**HTTP, Obsolete, Reference, header, request**

The obsolete `Cookie2` HTTP request header used to advise the server that the user agent understands "new-style" cookies, but nowadays user agents will use the [`Cookie`](cookie) header instead, not this one.

56

[DNT](dnt)

**DNT, HTTP, Reference, header**

The `DNT` (**D**o **N**ot **T**rack) request header indicates the user's tracking preference. It lets users indicate whether they would prefer privacy rather than personalized content.

57

[Date](date)

**General Header, HTTP, Reference, header**

The `Date` general HTTP header contains the date and time at which the message was originated.

58

[ETag](etag)

**HTTP, Reference, Response, header**

The `ETag` HTTP response header is an identifier for a specific version of a resource. It allows caches to be more efficient, and saves bandwidth, as a web server does not need to send a full response if the content has not changed. On the other side, if the content has changed, etags are useful to help prevent simultaneous updates of a resource from overwriting each other ("mid-air collisions").

59

[Early-Data](early-data)

**Client hints, HTTP, header, request**

The `Early-Data` header is set by an intermediate to indicates that the request has been conveyed in [TLS early data](https://developer.mozilla.org/en-US/docs/Web/Security/Transport_Layer_Security#TLS_1.3), and additionally indicates that an intermediary understands the [`425 (Too Early)`](../status/425) status code. The `Early-Data` header is not set by the originator of the request (i.e., a browser).

60

[Expect](expect)

**HTTP, HTTP Header, Reference, Request header**

The `Expect` HTTP request header indicates expectations that need to be fulfilled by the server in order to properly handle the request.

61

[Expect-CT](expect-ct)

**HTTP, Reference, header**

The `Expect-CT` header allows sites to opt in to reporting and/or enforcement of Certificate Transparency requirements, which prevents the use of misissued certificates for that site from going unnoticed.

62

[Expires](expires)

**Caching, HTTP, Response, header**

The `Expires` header contains the date/time after which the response is considered stale.

63

[Feature-Policy](feature-policy)

**Experimental, Feature Policy, Feature-Policy, HTTP, Reference, header**

The HTTP `Feature-Policy` header provides a mechanism to allow and deny the use of browser features in its own frame, and in iframes that it embeds.

64

[Feature-Policy: autoplay](feature-policy/autoplay)

**Directive, Feature Policy, Feature-Policy, HTTP, Reference, autoplay**

The HTTP [`Feature-Policy`](feature-policy) header `autoplay` directive controls whether the current document is allowed to autoplay media requested through the [`HTMLMediaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement) interface. When this policy is enabled and there were no user gestures, the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/API/Promise) returned by [`HTMLMediaElement.play()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/play) will reject with a `DOMException`. The `autoplay` attribute on [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) and [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) elements will be ignored.

65

[Feature-Policy: camera](feature-policy/camera)

**Directive, Feature Policy, Feature-Policy, HTTP, Reference, camera**

The HTTP [`Feature-Policy`](feature-policy) header `camera` directive controls whether the current document is allowed to use video input devices. When this policy is enabled, the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by [`MediaDevices.getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia) will reject with a `NotAllowedError`.

66

[Feature-Policy: encrypted-media](feature-policy/encrypted-media)

**Directive, EME, Feature Policy, Feature-Policy, HTTP, Reference**

The HTTP [`Feature-Policy`](feature-policy) header `encrypted-media` directive controls whether the current document is allowed to use the [Encrypted Media Extensions](https://developer.mozilla.org/en-US/docs/Web/API/Encrypted_Media_Extensions_API) API (EME). When this policy is enabled, the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/API/Promise) returned by [`Navigator.requestMediaKeySystemAccess()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/requestMediaKeySystemAccess) will reject with a `DOMException`.

67

[Feature-Policy: fullscreen](feature-policy/fullscreen)

**Feature Policy, Feature-Policy, HTTP, fullscreen, header**

The HTTP [`Feature-Policy`](feature-policy) header `fullscreen` directive controls whether the current document is allowed to use [`Element.requestFullScreen()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/requestFullScreen). When this policy is enabled, the returned [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) rejects with a [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError).

68

[Feature-Policy: geolocation](feature-policy/geolocation)

**Feature Policy, Feature-Policy, Geolocation, HTTP, header**

The HTTP [`Feature-Policy`](feature-policy) header `geolocation` directive controls whether the current document is allowed to use the [`Geolocation`](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation) Interface. When this policy is enabled, calls to [`getCurrentPosition()`](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/getCurrentPosition) and [`watchPosition()`](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/watchPosition) will cause those functions' callbacks to be invoked with a [`PositionError`](https://developer.mozilla.org/en-US/docs/Web/API/PositionError) code of `PERMISSION_DENIED`.

69

[Feature-Policy: microphone](feature-policy/microphone)

**Feature Policy, Feature-Policy, HTTP, header, microphone**

The HTTP [`Feature-Policy`](feature-policy) header `microphone` directive controls whether the current document is allowed to use audio input devices. When this policy is enabled, the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by [`MediaDevices.getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia) will reject with a `NotAllowedError`.

70

[Feature-Policy: midi](feature-policy/midi)

**Directive, Feature Policy, Feature-Policy, HTTP, MIDI, Reference**

The HTTP [`Feature-Policy`](feature-policy) header `midi` directive controls whether the current document is allowed to use the [Web MIDI API](https://developer.mozilla.org/en-US/docs/Web/API/Web_MIDI_API). When this policy is enabled, the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by [`Navigator.requestMIDIAccess()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/requestMIDIAccess) will reject with a `DOMException`.

71

[Feature-Policy: payment](feature-policy/payment)

**Directive, Feature Policy, Feature-Policy, HTTP, Payment Request API, Payments API, Reference**

The HTTP [`Feature-Policy`](feature-policy) header `payment` directive controls whether the current document is allowed to use the [Payment Request API](https://developer.mozilla.org/en-US/docs/Web/API/Payment_Request_API). When this policy is enabled, the [`PaymentRequest()`](https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest) constructor will throw a `SecurityError`.

72

[Feature-Policy: vr](feature-policy/vr)

**Directive, Feature Policy, Feature-Policy, HTTP, Reference, WebVR**

The HTTP [`Feature-Policy`](feature-policy) header `vr` directive controls whether the current document is allowed to use the [WebVR API](https://developer.mozilla.org/en-US/docs/Web/API/WebVR_API). When this policy is enabled, the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by [`Navigator.getVRDisplays()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getVRDisplays) will reject with a `DOMException`.

73

[document-domain](feature-policy/document-domain)

**Directive, Experimental, Feature Policy, Feature-Policy, HTTP, Reference, document-domain, header**

The HTTP [`Feature-Policy`](feature-policy) header `document-domain` directive controls whether the current document is allowed to set [`document.domain`](https://developer.mozilla.org/en-US/docs/Web/API/Document/domain). When this policy is enabled, attempting to set [`document.domain`](https://developer.mozilla.org/en-US/docs/Web/API/Document/domain) will fail and cause a `SecurityError` [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException) to be be thrown.

74

[Forwarded](forwarded)

**HTTP, HTTP Header, Reference, Request header, header**

The `Forwarded` header contains information from the client-facing side of proxy servers that is altered or lost when a proxy is involved in the path of the request.

75

[From](from)

**HTTP, Reference, header**

The `From` request header contains an Internet email address for a human user who controls the requesting user agent.

76

[Host](host)

**HTTP, Reference, header**

The `Host` request header specifies the domain name of the server (for virtual hosting), and (optionally) the TCP port number on which the server is listening.

77

[If-Match](if-match)

**Conditional Requests, HTTP, HTTP Header, Reference, Request header**

The `If-Match` HTTP request header makes the request conditional. For [`GET`](../methods/get) and [`HEAD`](../methods/head) methods, the server will send back the requested resource only if it matches one of the listed `ETags`. For [`PUT`](../methods/put) and other non-safe methods, it will only upload the resource in this case.

78

[If-Modified-Since](if-modified-since)

**Conditional Requests, HTTP, HTTP Header, Reference, Request header**

The `If-Modified-Since` request HTTP header makes the request conditional: the server will send back the requested resource, with a [`200`](../status/200) status, only if it has been last modified after the given date. If the request has not been modified since, the response will be a [`304`](../status/304) without any body; the [`Last-Modified`](last-modified) response header of a previous request will contain the date of last modification. Unlike [`If-Unmodified-Since`](if-unmodified-since), `If-Modified-Since` can only be used with a [`GET`](../methods/get) or [`HEAD`](../methods/head).

79

[If-None-Match](if-none-match)

**Conditional Requests, HTTP, HTTP Header, Reference, Request header**

The `If-None-Match` HTTP request header makes the request conditional. For [`GET`](../methods/get) and [`HEAD`](../methods/head) methods, the server will send back the requested resource, with a [`200`](../status/200) status, only if it doesn't have an [`ETag`](etag) matching the given ones. For other methods, the request will be processed only if the eventually existing resource's [`ETag`](etag) doesn't match any of the values listed.

80

[If-Range](if-range)

**Condtional Requests, HTTP, HTTP Header, Range Requests, Reference, Request header**

The `If-Range` HTTP request header makes a range request conditional: if the condition is fulfilled, the range request will be issued and the server sends back a [`206`](../status/206) `Partial Content` answer with the appropriate body. If the condition is not fulfilled, the full resource is sent back, with a [`200`](../status/200) `OK` status.

81

[If-Unmodified-Since](if-unmodified-since)

**HTTP, HTTP Header, Reference, Request header**

The `If-Unmodified-Since` request HTTP header makes the request conditional: the server will send back the requested resource, or accept it in the case of a [`POST`](../methods/post) or another non-[safe](https://developer.mozilla.org/en-US/docs/Glossary/safe) method, only if it has not been last modified after the given date. If the resource has been modified after the given date, the response will be a [`412`](../status/412) (Precondition Failed) error.

82

[Index](index)

**HTTP, HTTP Header, Index**

**Found 115 pages:**

83

[Keep-Alive](keep-alive)

**General Header, HTTP, HTTP Header, Reference**

The `Keep-Alive` general header allows the sender to hint about how the connection may be used to set a timeout and a maximum amount of requests.

84

[Large-Allocation](large-allocation)

**HTTP, HTTP Header, Non-standard, Reference, Response Header, header**

The non-standard `Large-Allocation` response header tells the browser that the page being loaded is going to want to perform a large allocation. It is currently only implemented in Firefox, but is harmless to send to every browser.

85

[Last-Modified](last-modified)

**HTTP, HTTP Header, Reference, Response Header**

The `Last-Modified` response HTTP header contains the date and time at which the origin server believes the resource was last modified. It is used as a validator to determine if a resource received or stored is the same. Less accurate than an [`ETag`](etag) header, it is a fallback mechanism. Conditional requests containing [`If-Modified-Since`](if-modified-since) or [`If-Unmodified-Since`](if-unmodified-since) headers make use of this field.

86

[Location](location)

**HTTP, HTTP Header, Reference, Response Header**

The `Location` response header indicates the URL to redirect a page to. It only provides a meaning when served with a `3xx` (redirection) or `201` (created) status response.

87

[Origin](origin)

**HTTP, Reference, header**

The `Origin` request header indicates where a fetch originates from. It doesn't include any path information, but only the server name. It is sent with [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS) requests, as well as with [`POST`](../methods/post) requests. It is similar to the [`Referer`](referer) header, but, unlike this header, it doesn't disclose the whole path.

88

[Pragma](pragma)

**Caching, Deprecated, HTTP, header, request**

The `Pragma` HTTP/1.0 general header is an implementation-specific header that may have various effects along the request-response chain. It is used for backwards compatibility with HTTP/1.0 caches where the `Cache-Control` HTTP/1.1 header is not yet present.

89

[Proxy-Authenticate](proxy-authenticate)

**HTTP, HTTP Header, Proxy, Reference, Response Header**

The HTTP `Proxy-Authenticate` response header defines the authentication method that should be used to gain access to a resource behind a [proxy server](https://developer.mozilla.org/en-US/docs/Glossary/proxy_server). It authenticates the request to the proxy server, allowing it to transmit the request further.

90

[Proxy-Authorization](proxy-authorization)

**HTTP, HTTP Header, Reference, Request header, header**

The HTTP `Proxy-Authorization` request header contains the credentials to authenticate a user agent to a proxy server, usually after the server has responded with a [`407`](../status/407) `Proxy Authentication Required` status and the [`Proxy-Authenticate`](proxy-authenticate) header.

91

[Public-Key-Pins](public-key-pins)

**HPKP, HTTP, Reference, Security, header**

The HTTP `Public-Key-Pins` response header associates a specific cryptographic public [key](https://developer.mozilla.org/en-US/docs/Glossary/key) with a certain web server to decrease the risk of [MITM](https://developer.mozilla.org/en-US/docs/Glossary/MITM) attacks with forged certificates. If one or several keys are pinned and none of them are used by the server, the browser will not accept the response as legitimate, and will not display it.

92

[Public-Key-Pins-Report-Only](public-key-pins-report-only)

**HPKP, HTTP, Security, header**

The HTTP `Public-Key-Pins-Report-Only` response header sends reports of pinning violation to the `report-uri` specified in the header but, unlike [`Public-Key-Pins`](public-key-pins) still allows browsers to connect to the server if the pinning is violated.

93

[Range](range)

**HTTP, HTTP Header, Range Requests, Reference, Request header**

The `Range` HTTP request header indicates the part of a document that the server should return. Several parts can be requested with one `Range` header at once, and the server may send back these ranges in a multipart document. If the server sends back ranges, it uses the [`206`](../status/206) `Partial Content` for the response. If the ranges are invalid, the server returns the [`416`](../status/416) `Range Not Satisfiable` error. The server can also ignore the `Range` header and return the whole document with a [`200`](../status/200) status code.

94

[Referer](referer)

**HTTP, Reference, header, referer, referrer**

The `Referer` request header contains the address of the previous web page from which a link to the currently requested page was followed. The `Referer` header allows servers to identify where people are visiting them from and may use that data for analytics, logging, or optimized caching, for example.

95

[Referrer-Policy](referrer-policy)

**HTTP, HTTP Header, Privacy, Reference, Referrer-Policy, Response, referrer**

The `Referrer-Policy` HTTP header governs which referrer information, sent in the [`Referer`](referer) header, should be included with requests made.

96

[Retry-After](retry-after)

**HTTP, Reference, Response, Response Header, header**

The `Retry-After` response HTTP header indicates how long the user agent should wait before making a follow-up request. There are three main cases this header is used:

97

[Sec-WebSocket-Accept](sec-websocket-accept)

**Draft, HTTP, NeedsCompatTable, NeedsContent, Reference, Sec-WebSocket-Accept, WebSockets, header**

The **Sec-WebSocket-Accept** header is used in the websocket opening handshake. It would appear in the response headers. That is, this is header is sent from server to client to inform that server is willing to initiate a websocket connection.

98

[Server](server)

**HTTP, Reference, header**

The `Server` header contains information about the software used by the origin server to handle the request.

99

[Server-Timing](server-timing)

**HTTP, Performance, Reference, header**

The `Server-Timing` header communicates one or more metrics and descriptions for a given request-response cycle. It is used to surface any backend server timing metrics (e.g. database read/write, CPU time, file system access, etc.) in the developer tools in the user's browser or in the [`PerformanceServerTiming`](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceServerTiming) interface.

100

[Set-Cookie](set-cookie)

**Cookies, HTTP, Reference, Response, header**

The `Set-Cookie` HTTP response header is used to send cookies from the server to the user agent.

101

[Set-Cookie2](set-cookie2)

**Cookies, HTTP, Obsolete, Reference, header**

The obsolete `Set-Cookie2` HTTP response header used to send cookies from the server to the user agent, but has been deprecated by the specification. Use [`Set-Cookie`](set-cookie) instead.

102

[SourceMap](sourcemap)

**HTTP, HTTP Header, Reference, Response Header, header**

The `SourceMap` [HTTP](../index) response header links generated code to a [source map](https://developer.mozilla.org/en-US/docs/Tools/Debugger/How_to/Use_a_source_map), enabling the browser to reconstruct the original source and present the reconstructed original in the debugger.

103

[Strict-Transport-Security](strict-transport-security)

**HSTS, HTTP, HTTPS, Security, header**

The `Strict-Transport-Security` response header (often abbreviated as [HSTS](https://developer.mozilla.org/en-US/docs/Glossary/HSTS)) lets a web site tell browsers that it should only be accessed using HTTPS, instead of using HTTP.

104

[TE](te)

**HTTP, Reference, header**

The `TE` request header specifies the transfer encodings the user agent is willing to accept. (you could informally call it *`Accept-Transfer-Encoding`*, which would be more intuitive).

105

[Timing-Allow-Origin](timing-allow-origin)

**CORS, HTTP, Reference, Timing-Allow-Origin, header**

The `Timing-Allow-Origin` response header specifies origins that are allowed to see values of attributes retrieved via features of the [Resource Timing API](https://developer.mozilla.org/en-US/docs/Web/API/Resource_Timing_API), which would otherwise be reported as zero due to cross-origin restrictions.

106

[Tk](tk)

**DNT, HTTP, Reference, Response, header, tracking**

The `Tk` response header indicates the tracking status that applied to the corresponding request.

107

[Trailer](trailer)

**HTTP, Reference, header**

The **Trailer** response header allows the sender to include additional fields at the end of chunked messages in order to supply metadata that might be dynamically generated while the message body is sent, such as a message integrity check, digital signature, or post-processing status.

108

[Transfer-Encoding](transfer-encoding)

**HTTP, Reference, header**

The `Transfer-Encoding` header specifies the form of encoding used to safely transfer the [entity](https://developer.mozilla.org/en-US/docs/Glossary/Entity_header) to the user.

109

[Upgrade-Insecure-Requests](upgrade-insecure-requests)

**HTTP, HTTPS, Security, header**

The HTTP `Upgrade-Insecure-Requests` request header sends a signal to the server expressing the client’s preference for an encrypted and authenticated response, and that it can successfully handle the [`upgrade-insecure-requests`](content-security-policy/upgrade-insecure-requests) [CSP](https://developer.mozilla.org/en-US/docs/Web/Security/CSP) directive.

110

[User-Agent](user-agent)

**HTTP, Reference, header**

The **User-Agent** request header contains a characteristic string that allows the network protocol peers to identify the application type, operating system, software vendor or software version of the requesting software user agent.

111

[Firefox user agent string reference](user-agent/firefox)

**Compatibility, Firefox, Firefox 4, Gecko, Gecko 2.0, Guide**

This document describes the user agent string used in Firefox 4 and later and applications based on [Gecko](https://developer.mozilla.org/en-US/docs/Mozilla/Gecko) 2.0 and later. For a breakdown of changes to the string in Gecko 2.0, see [Final User Agent string for Firefox 4](https://hacks.mozilla.org/2010/09/final-user-agent-string-for-firefox-4/) (blog post). See also this document on [user agent sniffing](../browser_detection_using_the_user_agent) and this [Hacks blog post](https://hacks.mozilla.org/2013/09/user-agent-detection-history-and-checklist/).

112

[Vary](vary)

**HTTP, Reference, Response, Response Header, header**

The `Vary` HTTP response header determines how to match future request headers to decide whether a cached response can be used rather than requesting a fresh one from the origin server. It is used by the server to indicate which headers it used when selecting a representation of a resource in a [content negotiation](../content_negotiation) algorithm.

113

[Via](via)

**HTTP, Reference, header**

The `Via` general header is added by proxies, both forward and reverse proxies, and can appear in the request headers and the response headers. It is used for tracking message forwards, avoiding request loops, and identifying the protocol capabilities of senders along the request/response chain.

114

[WWW-Authenticate](www-authenticate)

**HTTP, HTTP Header, Reference, Response Header, header**

The HTTP `WWW-Authenticate` response header defines the authentication method that should be used to gain access to a resource.

115

[Warning](warning)

**General Header, HTTP, Reference, header**

The `Warning` general HTTP header contains information about possible problems with the status of the message. More than one `Warning` header may appear in a response.

116

[X-Content-Type-Options](x-content-type-options)

**HTTP, HTTP Header, Reference, Response Header**

The `X-Content-Type-Options` response HTTP header is a marker used by the server to indicate that the [MIME types](../basics_of_http/mime_types) advertised in the [`Content-Type`](content-type) headers should not be changed and be followed. This allows to opt-out of [MIME type sniffing](../basics_of_http/mime_types#MIME_sniffing), or, in other words, it is a way to say that the webmasters knew what they were doing.

117

[X-DNS-Prefetch-Control](x-dns-prefetch-control)

**DNS, HTTP, header**

The `X-DNS-Prefetch-Control` HTTP response header controls DNS prefetching, a feature by which browsers proactively perform domain name resolution on both links that the user may choose to follow as well as URLs for items referenced by the document, including images, CSS, JavaScript, and so forth.

118

[X-Forwarded-For](x-forwarded-for)

**HTTP, HTTP Header, Non-standard, Reference, Request header, header**

The `X-Forwarded-For` (XFF) header is a de-facto standard header for identifying the originating IP address of a client connecting to a web server through an HTTP proxy or a load balancer. When traffic is intercepted between clients and servers, server access logs contain the IP address of the proxy or load balancer only. To see the original IP address of the client, the `X-Forwarded-For` request header is used.

119

[X-Forwarded-Host](x-forwarded-host)

**HTTP, HTTP Header, Non-standard, Reference, Request header, header**

The `X-Forwarded-Host` (XFH) header is a de-facto standard header for identifying the original host requested by the client in the [`Host`](host) HTTP request header.

120

[X-Forwarded-Proto](x-forwarded-proto)

**HTTP, HTTP Header, Non-standard, Reference, Request header, header**

The `X-Forwarded-Proto` (XFP) header is a de-facto standard header for identifying the protocol (HTTP or HTTPS) that a client used to connect to your proxy or load balancer. Your server access logs contain the protocol used between the server and the load balancer, but not the protocol used between the client and the load balancer. To determine the protocol used between the client and the load balancer, the `X-Forwarded-Proto` request header can be used.

121

[X-Frame-Options](x-frame-options)

**Gecko, HAProxy, HTTP, Response Header, Security, nginx**

The `X-Frame-Options` [HTTP](../index) response header can be used to indicate whether or not a browser should be allowed to render a page in a [`<frame>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frame), [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe), [`<embed>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed) or [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object) . Sites can use this to avoid [clickjacking](https://en.wikipedia.org/wiki/clickjacking) attacks, by ensuring that their content is not embedded into other sites.

122

[X-XSS-Protection](x-xss-protection)

**HTTP, Reference, Security, XSS, header**

The HTTP `X-XSS-Protection` response header is a feature of Internet Explorer, Chrome and Safari that stops pages from loading when they detect reflected cross-site scripting ([XSS](https://developer.mozilla.org/en-US/docs/Glossary/XSS)) attacks. Although these protections are largely unnecessary in modern browsers when sites implement a strong [`Content-Security-Policy`](content-security-policy) that disables the use of inline JavaScript (`'unsafe-inline'`), they can still provide protections for users of older web browsers that don't yet support [CSP](https://developer.mozilla.org/en-US/docs/Glossary/CSP).

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Index$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Index" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Index</a>
