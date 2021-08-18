&lt;iframe&gt;: The Inline Frame element
========================================

The `<iframe>` represents a nested [browsing context](https://developer.mozilla.org/en-US/docs/Glossary/Browsing_context), embedding another HTML page into the current one.

Each embedded browsing context has its own [session history](https://developer.mozilla.org/en-US/docs/Web/API/History) and [document](https://developer.mozilla.org/en-US/docs/Web/API/Document). The browsing context that embeds the others is called the *parent browsing context*. The *topmost* browsing context — the one with no parent — is usually the browser window, represented by the [`Window`](https://developer.mozilla.org/en-US/docs/Web/API/Window) object.

Because each browsing context is a complete document environment, every `<iframe>` in a page requires increased memory and other computing resources. While theoretically you can use as many `<iframe>`s as you like, check for performance problems.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, embedded content, interactive content, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td>None.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts embedded content.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><code>application</code>, <code>document</code>, <code>img</code>, <code>none</code>, <code>presentation</code></td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement"><code>HTMLIFrameElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

`allow`  
Specifies a [feature policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Feature_Policy) for the `<iframe>`. The policy defines what features are available to the `<iframe>` based on the origin of the request (e.g. access to the microphone, camera, battery, web-share API, etc.).  
  
For more information and examples see: [Using Feature Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Feature_Policy/Using_Feature_Policy) &gt; [The iframe allow attribute](https://developer.mozilla.org/en-US/docs/Web/HTTP/Feature_Policy/Using_Feature_Policy#the_iframe_allow_attribute).

`allowfullscreen`  
Set to `true` if the `<iframe>` can activate fullscreen mode by calling the [`requestFullscreen()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/requestFullScreen) method.

This attribute is considered a legacy attribute and redefined as `allow="fullscreen"`.

`allowpaymentrequest`  
Set to `true` if a cross-origin `<iframe>` should be allowed to invoke the [Payment Request API](https://developer.mozilla.org/en-US/docs/Web/API/Payment_Request_API).

This attribute is considered a legacy attribute and redefined as `allow="payment"`.

 `csp` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
A [Content Security Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP) enforced for the embedded resource. See [`HTMLIFrameElement.csp`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement/csp) for details.

`height`  
The height of the frame in CSS pixels. Default is `150`.

 `loading` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Indicates how the browser should load the iframe:

-   `eager`: Load the iframe immediately, regardless if it is outside the visible viewport (this is the default value).
-   `lazy`: Defer loading of the iframe until it reaches a calculated distance from the viewport, as defined by the browser.

`name`  
A targetable name for the embedded browsing context. This can be used in the `target` attribute of the [`<a>`](a), [`<form>`](form), or [`<base>`](base) elements; the `formtarget` attribute of the [`<input>`](input) or [`<button>`](button) elements; or the `windowName` parameter in the [`window.open()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/open) method.

`referrerpolicy`  
Indicates which [referrer](https://developer.mozilla.org/en-US/docs/Web/API/Document/referrer) to send when fetching the frame's resource:

-   `no-referrer`: The [`Referer`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer) header will not be sent.
-   `no-referrer-when-downgrade` (default): The [`Referer`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer) header will not be sent to [origin](https://developer.mozilla.org/en-US/docs/Glossary/Origin)s without [TLS](https://developer.mozilla.org/en-US/docs/Glossary/TLS) ([HTTPS](https://developer.mozilla.org/en-US/docs/Glossary/https)).
-   `origin`: The sent referrer will be limited to the origin of the referring page: its [scheme](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL), [host](https://developer.mozilla.org/en-US/docs/Glossary/Host), and [port](https://developer.mozilla.org/en-US/docs/Glossary/Port).
-   `origin-when-cross-origin`: The referrer sent to other origins will be limited to the scheme, the host, and the port. Navigations on the same origin will still include the path.
-   `same-origin`: A referrer will be sent for [same origin](https://developer.mozilla.org/en-US/docs/Glossary/Same-origin_policy), but cross-origin requests will contain no referrer information.
-   `strict-origin`: Only send the origin of the document as the referrer when the protocol security level stays the same (HTTPS→HTTPS), but don't send it to a less secure destination (HTTPS→HTTP).
-   `strict-origin-when-cross-origin`: Send a full URL when performing a same-origin request, only send the origin when the protocol security level stays the same (HTTPS→HTTPS), and send no header to a less secure destination (HTTPS→HTTP).
-   `unsafe-url`: The referrer will include the origin *and* the path (but not the [fragment](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/hash), [password](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/password), or [username](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/username)). **This value is unsafe**, because it leaks origins and paths from TLS-protected resources to insecure origins.

`sandbox`  
Applies extra restrictions to the content in the frame. The value of the attribute can either be empty to apply all restrictions, or space-separated tokens to lift particular restrictions:

-   `allow-downloads-without-user-activation` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>: Allows for downloads to occur without a gesture from the user.
-   `allow-downloads`: Allows for downloads to occur with a gesture from the user.
-   `allow-forms`: Allows the resource to submit forms. If this keyword is not used, form submission is blocked.
-   `allow-modals`: Lets the resource [open modal windows](https://html.spec.whatwg.org/multipage/origin.html#sandboxed-modals-flag).
-   `allow-orientation-lock`: Lets the resource [lock the screen orientation](https://developer.mozilla.org/en-US/docs/Web/API/Screen/lockOrientation).
-   `allow-pointer-lock`: Lets the resource use the [Pointer Lock API](https://developer.mozilla.org/en-US/docs/Web/API/Pointer_Lock_API).
-   `allow-popups`: Allows popups (such as `window.open()`, `target="_blank"`, or `showModalDialog()`). If this keyword is not used, the popup will silently fail to open.
-   `allow-popups-to-escape-sandbox`: Lets the sandboxed document open new windows without those windows inheriting the sandboxing. For example, this can safely sandbox an advertisement without forcing the same restrictions upon the page the ad links to.
-   `allow-presentation`: Lets the resource start a [presentation session](https://developer.mozilla.org/en-US/docs/Web/API/PresentationRequest).
-   `allow-same-origin`: If this token is not used, the resource is treated as being from a special origin that always fails the [same-origin policy](https://developer.mozilla.org/en-US/docs/Glossary/Same-origin_policy) (potentially preventing access to [data storage/cookies](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy#cross-origin_data_storage_access) and some JavaScript APIs).
-   `allow-scripts`: Lets the resource run scripts (but not create popup windows).
-   `allow-storage-access-by-user-activation` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>: Lets the resource request access to the parent's storage capabilities with the [Storage Access API](https://developer.mozilla.org/en-US/docs/Web/API/Storage_Access_API).
-   `allow-top-navigation`: Lets the resource navigate the top-level browsing context (the one named `_top`).
-   `allow-top-navigation-by-user-activation`: Lets the resource navigate the top-level browsing context, but only if initiated by a user gesture.

**Notes about sandboxing:**
-   When the embedded document has the same origin as the embedding page, it is **strongly discouraged** to use both `allow-scripts` and `allow-same-origin`, as that lets the embedded document remove the `sandbox` attribute — making it no more secure than not using the `sandbox` attribute at all.
-   Sandboxing is useless if the attacker can display content outside a sandboxed `iframe` — such as if the viewer opens the frame in a new tab. Such content should be also served from a *separate origin* to limit potential damage.
-   The `sandbox` attribute is unsupported in Internet Explorer 9 and earlier.

`src`  
The URL of the page to embed. Use a value of `about:blank` to embed an empty page that conforms to the [same-origin policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy#inherited_origins). Also note that programmatically removing an `<iframe>`'s src attribute (e.g. via [`Element.removeAttribute()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttribute)) causes `about:blank` to be loaded in the frame in Firefox (from version 65), Chromium-based browsers, and Safari/iOS.

`srcdoc`  
Inline HTML to embed, overriding the `src` attribute. If a browser does not support the `srcdoc` attribute, it will fall back to the URL in the `src` attribute.

`width`  
The width of the frame in CSS pixels. Default is `300`.

### Deprecated attributes

These attributes are deprecated and may no longer be supported by all user agents. You should not use them in new content, and try to remove them from existing content.

 `align` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The alignment of this element with respect to the surrounding context.

 `frameborder` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The value `1` (the default) draws a border around this frame. The value `0` removes the border around this frame, but you should instead use the CSS property [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) to control `<iframe>` borders.

 `longdesc` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
A URL of a long description of the frame's content. Due to widespread misuse, this is not helpful for non-visual browsers.

 `marginheight` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The amount of space in pixels between the frame's content and its top and bottom borders.

 `marginwidth` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The amount of space in pixels between the frame's content and its left and right borders.

 `scrolling` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Indicates when the browser should provide a scrollbar for the frame:

-   `auto`: Only when the frame's content is larger than its dimensions.
-   `yes`: Always show a scrollbar.
-   `no`: Never show a scrollbar.

### Non-standard attributes

 `mozbrowser` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
See [bug 1318532](https://bugzilla.mozilla.org/show_bug.cgi?id=1318532) for exposing this to WebExtensions in Firefox.

Makes the `<iframe>` act like a top-level browser window. See [Browser API](https://developer.mozilla.org/en-US/docs/Mozilla/Gecko/Chrome/API/Browser_API) for details.  
**Available only to [WebExtensions](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions).**

Scripting
---------

Inline frames, like [`<frame>`](frame) elements, are included in the [`window.frames`](https://developer.mozilla.org/en-US/docs/Web/API/Window/frames) pseudo-array.

With the DOM [`HTMLIFrameElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement) object, scripts can access the [`window`](https://developer.mozilla.org/en-US/docs/Web/API/Window) object of the framed resource via the [`contentWindow`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement/contentWindow) property. The [`contentDocument`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLIFrameElement/contentDocument) property refers to the `document` inside the `<iframe>`, same as `contentWindow.document`.

From the inside of a frame, a script can get a reference to its parent window with [`window.parent`](https://developer.mozilla.org/en-US/docs/Web/API/Window/parent).

Script access to a frame's content is subject to the [same-origin policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy). Scripts cannot access most properties in other `window` objects if the script was loaded from a different origin, including scripts inside a frame accessing the frame's parent. Cross-origin communication can be achieved using [`Window.postMessage()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage).

Positioning and scaling
-----------------------

As a [replaced element](https://developer.mozilla.org/en-US/docs/Web/CSS/Replaced_element), the position, alignment, and scaling of the embedded document within the `<iframe>` element's box, can be adjusted with the [`object-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-position) and [`object-fit`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit) properties.

Examples
--------

### A simple &lt;iframe&gt;

An `<iframe>` in action. After creating the frame, when the user clicks a button, its title is displayed in an alert.

#### HTML

    <iframe src="https://mdn-samples.mozilla.org/snippets/html/iframe-simple-contents.html"
                title="iframe Example 1" width="400" height="300">
    </iframe>

#### Result

Accessibility concerns
----------------------

People navigating with assistive technology such as a screen reader can use the [`title` attribute](../global_attributes/title) on an `<iframe>` to label its content. The title's value should concisely describe the embedded content:

    <iframe title="Wikipedia page for Avocados" src="https://en.wikipedia.org/wiki/Avocado"></iframe>

Without this title, they have to navigate into the `<iframe>` to determine what its embedded content is. This context shift can be confusing and time-consuming, especially for pages with multiple `<iframe>`s and/or if embeds contain interactive content like video or audio.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-referrer-policy/#referrer-policy-delivery-referrer-attribute">Referrer Policy<br />
<span class="small">The definition of 'referrerpolicy attribute' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Added the <code>referrerpolicy</code> attribute.</td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/iframe-embed-object.html#the-iframe-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;iframe&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/semantics-embedded-content.html#the-iframe-element">HTML5<br />
<span class="small">The definition of '&lt;iframe&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html401/present/frames.html#h-16.5">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;iframe&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://w3c.github.io/screen-orientation/">Screen Orientation API</a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds <code>allow-orientation-lock</code> to the <code>sandbox</code> attribute.</td></tr></tbody></table>

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

`iframe`

1

12

Yes

The `resize` CSS property doesn't have any effect on this element due to [bug 680823](https://bugzil.la/680823).

Yes

Yes

Yes

Safari has a [bug](https://www.quirksmode.org/bugreports/archives/2005/02/hidden_iframes.html) that prevents iframes from loading if the `iframe` element was hidden when added to the page. `iframeElement.src = iframeElement.src` should cause it to load the iframe.

Yes

Yes

Yes

The `resize` CSS property doesn't have any effect on this element due to [bug 680823](https://bugzil.la/680823).

Yes

Yes

Safari has a [bug](https://www.quirksmode.org/bugreports/archives/2005/02/hidden_iframes.html) that prevents iframes from loading if the `iframe` element was hidden when added to the page. `iframeElement.src = iframeElement.src` should cause it to load the iframe.

Yes

`align`

1

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`allow`

60

79

74

No

47

11.1

60

60

No

44

11.3

8.0

`allowfullscreen`

27

17-38

≤79

12-79

18

9

11

≤15

15-25

7

Yes

37

37-38

27

18-38

18

9

≤14

14-25

7

Yes

1.5

1.0-3.0

`allowpaymentrequest`

No

No

56-83

No

No

No

No

No

56-83

No

No

No

`aspect_ratio_computed_from_attributes`

79

79

71

69-71

No

66

14

79

79

79

57

14

12.0

`external_protocol_urls_blocked`

?

?

67

?

?

?

?

?

67

?

?

?

`frameborder`

1

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`height`

1

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`loading`

77

79

No

See [bug 1622090](https://bugzil.la/1622090).

No

64

No

See [bug 196698](https://webkit.org/b/196698)

77

77

No

See [bug 1622090](https://bugzil.la/1622090).

55

No

See [bug 196698](https://webkit.org/b/196698)

12.0

`longdesc`

1

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`marginheight`

1

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`marginwidth`

1

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`name`

1

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`referrerpolicy`

51

79

50

No

38

11.1

51

51

50

41

No

7.2

`sandbox`

4

12

17

10

15

5

Yes

Yes

17

?

4.2

Yes

`sandbox-allow-downloads`

83

83

82

No

?

No

83

83

82

?

No

?

`sandbox-allow-modals`

?

?

49

No

?

?

?

?

49

?

?

?

`sandbox-allow-popups`

Yes

≤18

28

?

Yes

?

Yes

Yes

27

?

?

Yes

`sandbox-allow-popups-to-escape-sandbox`

46

79

49

No

32

?

46

46

49

32

?

5.0

`sandbox-allow-presentation`

53

79

50

No

40

?

No

53

50

41

?

6.0

`sandbox-allow-same-origin`

Yes

Chrome 70 and earlier block script execution without `allow-scripts`, even if `allow-same-origin` is set. For example, any bound handlers for click events of nodes inside an iframe throw an error for blocked script execution.

Yes

Yes

Yes

Yes

Yes

Safari blocks script execution without `allow-scripts` even if `allow-same-origin` is set. For example, any bound handlers for click events of nodes inside an iframe throw an error for blocked script execution.

Yes

Yes

Yes

Yes

Yes

Yes

`sandbox-allow-storage-access-by-user-activation`

No

No

65

No

No

11.1

No

No

65

No

11.3

No

`sandbox-allow-top-navigation-by-user-activation`

58

79

79

No

45

11.1

Not initially available in 11.1, but added in sub-version 13605.1.33.1.2.

58

58

79

43

?

7.0

`scrolling`

1

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`src`

1

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`srcdoc`

20

79

25

No

15

6

37

25

25

?

?

1.5

`width`

1

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [Privacy, permissions, and information security](https://developer.mozilla.org/en-US/docs/Web/Privacy)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe</a>
