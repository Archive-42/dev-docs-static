Request.context
===============

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The deprecated `context` read-only property of the [`Request`](../request) interface contains the context of the Request (e.g., `audio`, `image`, `iframe`). This defines what sort of resource is being fetched. This has been replaced by the [`destination`](destination) property.

The context of a request is only relevant in the [ServiceWorker API](../service_worker_api); a service worker can make decisions based on whether the URL is for an image, or an embeddable object such as a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video), <span class="page-not-created">`iframe`</span>, etc.

**Note**: You can find a full list of the different available contexts including associated context frame types, CSP directives, and platform feature examples in the [Fetch spec request context](https://fetch.spec.whatwg.org/#concept-request-context) section.

Syntax
------

    var myContext = request.context;

### Value

A <span class="page-not-created">`RequestContext`</span> value.

Example
-------

In the following snippet, we create a new request using the [`Request.Request()`](request) constructor (for an image file in the same directory as the script), then save the request context in a variable:

    var myRequest = new Request('flowers.jpg');
    var myContext = myRequest.context; // returns the empty string by default

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

`context`

42-46

?

39-42

see [bug 1188062](https://bugzil.la/1188062) for more information.

No

28-29

No

42-46

42-46

No

No

No

4.0-5.0

See also
--------

-   [ServiceWorker API](../service_worker_api)
-   [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
-   [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Request/context" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Request/context</a>
